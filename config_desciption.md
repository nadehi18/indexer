# Config Option Descriptions:

|Setting         | Setting Description |
|--------------------------|-----------------------------------------------------------------------------------------------------------------|
|html-folder| This is the folder to find HTML files to index|
|index-file| This is the name of the HTML file which will contain the list of links to the indexed files|
|html-head-file| This is the name of the file (within the indexer-resources folder) which is the code to be added to the indexed files when using the head option|
|html-header-file| This is the name of the file (within the indexer-resources folder) which is the code to be added to the indexed files when using the header option|
|html-footer-file| This is the name of the file (within the indexer-resources folder) which is the code to be added to the indexed files when using the footer option|
|note-item-file| This is the name of the file (within the indexer-resources folder) which is the code to be used as the template for the item link|
|note-category-file| This is the name of the file (within the indexer-resources folder) which is the code to be used as the template for a category which is basically an HTML separator|
|head-enabled| A boolean which denotes whether the tags denoted by the head options are enabled|
|head-start| The tag to mark the location start writing to in the indexed HTML files.  (Note: Should be unique)|
|head-end| The tag to end the writing to in the indexed HTML files, when used whatever is contained between the start and end tags is overwritten by the contents of the html-head-file.  (Note: Should be unique)|
|header-enabled| A boolean which denotes whether the tags denoted by the header options are enabled|
|header-start| The tag to mark the location start writing to in the indexed HTML files.  (Note: Should be unique)|
|header-end| The tag to end the writing to in the indexed HTML files, when used whatever is contained between the start and end tags is overwritten by the contents of the html-header-file.  (Note: Should be unique)|
|footer-enabled| A boolean which denotes whether the tags denoted by the footer options are enabled|
|footer-start| The tag to mark the location start writing to in the indexed HTML files.  (Note: Should be unique)|
|footer-end| The tag to end the writing to in the indexed HTML files, when used whatever is contained between the start and end tags is overwritten by the contents of the html-footer-file.  (Note: Should be unique)|
