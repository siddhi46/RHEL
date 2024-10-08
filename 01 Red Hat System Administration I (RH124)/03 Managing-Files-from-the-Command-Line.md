cd /
tree

cd /
sudo tree

/usr - installed softwares
/usr/bin - user commands
/usr/sbin - system admin commands
/usr/local - local customized softwares


/etc - config files
/var - boot,web content, log files, databases
/run - runtime data, contents recreated at boot
/var/run & /var/lock -earler RHEL
/home
/root - home directory for admin,root 
/tmp - 10 days deleted
/var/tmp - 30 days delete

/boot - files needed to start boot process
/dev - system access hardware/device files


touch A.txt a.txt

pwd
ls
cd

ls -l
ls -a
ls -R

cd .
cd .. 

cd
cd ..
pwd
cd ..
pwd
cd ..


*Command Line File Management*

mkdir directory
cp file new-file
cp -r directory new-directory
mv file new-file
rm file
rm -r directory
rmdir directory

mkdir Downloads/New
ls -R Downloads

mkdir -p Download/New-Directory

mkdir a b c
mkdir -p Downloads/a Downloads/b Downloads/c
ls -R Documents Downloads

cp a.txt b.txt new-f bf

// rename file
mv a.txt ab.txt

ls a
mv a.txt a

// Move File to Directories

ls -r new
mkdir new/hello
ls -r new
ls
mv c.txt new/hello
ls -R new

// Removing files
ls -R
rm 
mkdir new
rm new
rm -r new


ls
rm -ri directory
y

rmdir empty-dir


// Creating links between files
//hardlink

ln a.txt path/a.txt
ls -l a.txt
ls -il a.txt

df - file system

//softlink

ln -s b.txt path/b-soft.txt

// Pattern Matching
* - any string of zero or more characters
? - any single character
[abc]
[!abc]
[^abc]
[[:alpha:]]
[[:lower:]]
[[:upper:]]
[[:alnum:]]
[[:punct:]]
[[:digit:]]
[[:space:]]

//example
touch 1 2 3 New NEW new
ls *[[:digit:]]*
ls *[[:upper:]]*
ls *[[:lower:]]*

mkdir india
touch rohit rahul kishan virat gill shreyas surya jadeja ashwin shami bumrah yadav siraj
ls r* // starting with r
ls *r // ending with r
ls *r*
ls [ra]*
ls ?????
ls ????

//Brace Expansion
echo "Hello"
echo {Sun,Mon,Tue}Day
echo {a..z}.txt
echo {1..10}.txt
echo {a,b}{1,2}.txt

// create & delete multiple files using braces
mkdir {5,6,7}
ls
rm -rf {5,6,7}

// example
mkdir RHEL{6,7,8}
ls
rm -rf RHEL{6,7,8}

// example
touch {a..z}
ls
rm {a..z}
ls
 
// Vriable Expansion
// shell variable - VARIABLEName=Value
a=true
echo $a

trophy=WC
echo trophy
echo $trophy
history


// Command Substitution
date
date +%A
echo Today is $(date +%A).
echo Time is $(date +%M) Minutes past $(date +%l%p).

// Protecting Characters
echo The value of $HOME is your Home Directory.
echo The value of \$HOME is your Home Directory.

history -w /dev/stdout





 
