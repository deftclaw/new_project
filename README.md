# New Project  
_Work on projects in memory, save to secure-compressed files_  

## Dependencies:  
  - `direnv`  
  - `gpg` and a private-key setup for encryption  
  - `tar` should already be built-in to Unix

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

## Usage:  
__Creating a new Project:__  
Start in $HOME/code: `cd $HOME/code`  
Initilize to RAM: `. proj -n some_project_name`  
  - Because we 'sourced' the script it should navigate you to the folder automatically.
Make some changes to the project (optional)  

__Save & Initialize static Directory:__  
__Set GPG environment variable:__ `GPG=deftclaw` IMPORTANT!  
Navigate up once from the project root: `cd ..` __OR__ `cd $TMP`  
Source the 'save' file: `. save`  
This will prompt you for a tag to name the file, but is not necessary.  

## Installation:  
1. Clone this repo (recommended to memory): `cd /tmp/ && git clone https://github.com/deftclaw/new_project`  
2. Enter project directory and update GPG: `cd new_project && GPG=deftclaw` <- use your PGP key  
3. The 'save' script installs the rest of the tools: `. save`  
