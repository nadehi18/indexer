


# Indexer 
<img width=100px src="https://raw.githubusercontent.com/nadehi18/social-templates/master/codecard-python.png">

An editor and indexer for static HTML site pages.

Scans a directory for .html files and changes certain sections of the file based on tags which are set in the config.
Then adds a listing for those files in another html file which creates a list of links to those files.

## Example

I use this to add Boostnote exported HTML notes to my webpage.
<img src="https://raw.githubusercontent.com/nadehi18/Indexer/master/examples/notes.png">

Each note has my navigation header inserted into the file and is changed to be responsive:
<img src="https://raw.githubusercontent.com/nadehi18/Indexer/master/examples/example_note.png">


## Usage

HTML files which are being indexed use the following naming scheme:

For categorization:
```
categoryname-itemname.html
```
For no category:
```
itemname.html
```


First setup the config file (indexer.config) and place it in the indexer-resources/ folder.
Here is an example of a config file:

```
html-folder: note-files
index-file: notes.html
note-item-file: item.html
note-category-file: category.html

*OPERATION* {
    file:  head.html
    start: <head>
    end:   </head>
}

*OPERATION* {
    file:  header.html
    start: <body>
}

*OPERATION* {
    file:  footer.html
    start: </body>
}
```

Here are the main config file options:
|Setting         | Setting Description |
|--------------------------|-----------------------------------------------------------------------------------------------------------------|
|```html-folder```| This is the folder to find HTML files to index|
|```index-file```| This is the name of the HTML file which will contain the list of links to the indexed files|
|```note-item-file```| This is the name of the file (within the indexer-resources folder) which is the code to be used as the template for the item link|
|```note-category-file```| This is the name of the file (within the indexer-resources folder) which is the code to be used as the template for a category which is basically an HTML separator|

Operations are defined with teh ```*OPERATION*``` keyword and confined by braces.
Operations should be defined in order that the HTML tags will be found in the HTML file.
Not all operation options need to be set but the ```file``` and ```start``` options must be set.

|Setting     | Setting Description |
|-----------------|------------------------------------------------|
| ```file``` | The filename of the HTML template to be used for the operation |
| ```start``` | The HTML tag that will be replaced with the contents of ```file``` |
| ```end``` | The HTML tag that allows for deletion of all text between itself and the ```start``` tag to be deleted, including the tag itself |

Next, add your template HTML files into the indexer-resources/ folder.

There are certain markers in the files to use:
| Marker | Marker Description | Where it can be used |
|--------|--------------------|----------------------|
| ```<!--*NOTENAME*-->``` | References the name of the note | note-item-file |
| ```<!--*NOTEURL*-->```  | References the path to the note | note-item-file |
| ```<!--*CATEGORYNAME*-->``` | References the name of the category | note-category-file |
| ```<!--*STARTEDIT*-->``` | Marks the beginning of the list of links | index-file |
| ```<!--*ENDEDIT*-->``` | Marks the end of the list of links | index-file |
| ```<!--*INDEXED*-->``` | Marks file as indexed (automatically added) | Indexed HTML files |

## Executing

The files to be indexed should be in the directory denoted by the html-folder setting in the config.
Then simply:
```
python indexer.py
```
With no options, it should output the following for every filename:
```
Indexed "note-files/category-notename.html" Successfully
```
