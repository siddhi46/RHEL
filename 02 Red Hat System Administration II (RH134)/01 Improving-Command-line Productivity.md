// Improving Command-line Productivity   
// Intstall pwsh

sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.4.2/powershell-7.4.2-1.rh.x86_64.rpm -y

#! bin/bash
which hello
echo $PATH
echo "Hello World"
cat ~/bin/hello
#!/bin/bash
echo "Hello World"
echo "ERROR: Houston, we have a problem." >&2

hello 2> hello.log

cat hello.log

echo "" >> ~/output.txt

chmod a+x firstscript. sh
. /firstscript.sh


// RUNNING COMMANDS MORE EFFICIENTLY USING LOOPS

for VARIABLE in LIST; fo
COMMAND VARIABLE
done

for HOST in host1 host2 host3; do echo $HOST; done

for HOST in host{1, 2,3} ; do echo $HOST; done

for HOST in host{1.. 3} ; do echo $HOST; done

for FILE in file*; do ls $FILE; done

for FILE in file{a..c} ; do ls $FILE; done

for PACKAGE in $(rpm -qa | grep kernel); \ do echo "$PACKAGE was installed on \ $(date -d @$(rpm -q --qf "%{INSTALLTIME}\n" $PACKAGE))"; done

for EVEN in $(seq 2 2 10); do echo "$EVEN"; done

// Using Exit Codes With a Script
cat hello
#!/bin/bash
echo "Hello, world"
exit 0

./hello

echo $?

// Test Command
test 1 -gt 0 ; echo $?

test 0 -gt 1 ; echo $?

[ 1 -eq 1 ]; echo $?

[ 1 -ne 1 ]; echo $?

[ 8 -gt 2 ]; echo $?

[ 2 -ge 2 ]; echo $?

[ 2 -lt 2 ]; echo $?

[ 1 -lt 2 ]; echo $?

// Bash String Comparison
[ abc = abc ]; echo $?

[ abc == def ]; echo $?

[ abc != def ]; echo $?

// Bash String Unary Operator
STRING=''; [ -z "$STRING" ]; echo $?

STRING='abc'; [ -n "$STRING" ]; echo $?

// CONDITIONAL STRUCTURES 
// Using if then
if <CONDITION>; then
 <STATEMENT>
 ...
 <STATEMENT>
fi

// example
systemctl is-active psacct > /dev/null 2>&1

if [ $? -ne 0 ]; then
sudo systemctl start psacct
fi

// Using the if/then/else Construct
if <CONDITION>; then
 <STATEMENT>
 ...
 <STATEMENT>
 else
 <STATEMENT>
 ...
 <STATEMENT>
fi

// example
systemctl is-active psacct > /dev/null 2>&1
if [ $? -ne 0 ]; then
sudo systemctl start psacct
else
sudo systemctl stop psacct
fi

// Using the if/then/elif/then/else Construct


// Matching text in command line using Regular Expressions

grep '^computer' /usr/share/dict/words

ps aux | grep chrony

cat /etc/httpd/conf/httpd.conf

grep - iserverroot /etc/httpd/conf/httpd.conf

cat /etc/hosts
grep - v - i server /etc/hosts

cat /etc/etgertypes

grep - v '^[#;]' /etc/etgertypes

cat /var/log/secure \
vim /var/log/boot.log

less /var/log/messages

man regex
man grep





 