// output redirection

date > /tmp/saved-timestamp
tail -n 100 /var/log/dmesg > /tmp/last-100-boot-messages
cat file1 file2 file3 file4 > /tmp/all-four-in-one
ls -a > /tmp/my-file-names

echo "new-line info" >> /tmp/many-lines-info

diff previous-file current-file >> /tmp/tracking-changes-made

// errors

find /etc -name passwd 2> /tmp/errors

find /etc -name passwd > /tmp/output 2> /tmp/errors

find /etc -name passwd > /tmp/output 2> /dev/null  //ignore and discard error messages

find /etc -name passwd &> /temp/save-both  //save output & errors together

find /etc -name passwd >> /tmp/save-both 2>&1 // append output & generated errors to existing file

//pipeline

ls -l /usr/bin | less
ls | wc -l
ls -l | head -n 10 > /tmp/ten-last-changed-files

//pipeline, redirection and the tee command

ls > /tmp/saved-output | less

// pipeline, tee commans
ls -l | tee /tmp/saved-output | less
ls -t | head -n 10 | tee /tmp/ten-last-changed-files


// Editing Text files from shell prompt
vim 
vim filename
vi --version 
vim --version
:wq
i
v
esc

//Editinng Text files from the shell

// Assigning Values to Variables
COUNT=40 fisrt_name=Atul
file1=/tmp/abc
_ID=RH123

set | less

// Retrieving Values with Variable Expansion

COUNT =40
echo COUNT
file1=/tmp/tmp.z9pXW0HqcC
ls -l $file1
rm $file1

// Configure Programs with Environment Variables
EDITOR=vim
export EDITOR
      OR
export EDITOR=vim

export EDITOR=nano

vim filename
vi - - version
vim - - version

// 
Setting Default Text Editor
export EDITOR=nano
