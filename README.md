# New Project  
_Work on projects in memory, save to secure-compressed files_  

### Synopsis: 
Working from memory saves loading times and drive space. It is effective for enhancing the
speed of everything from version control, to re-compiling and file-watchers. Memory is simply
orders-of-magnitude faster than even SSD memory. Furthermore SSDs are subject to limmited read
 / write cycles unlike your RAM.  

With 'New Project' all of your develompent muck-arounds happen only to your ephemeral memory.
If you have to edit a file over again (dang semi-colons), those additional writes are happening
in memory and not on your limmited disk. Then we only 'save to disk' when calling the `. save`
script. This action compresses and encrypts the project while its still in your limmited-permission
temp-folder before copying it to the actual disk. This way your project takes up very little space
and is only accessible to you, (or whoever has your private PGP key).
