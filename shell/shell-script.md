
# About shell in linux
#!/bin/bash
echo "hello world"

## Execute shell script
–  bash hello.sh
–  sh hello.sh
–  ./hello.sh

## If condition
if <condition> then
	command1
	command2
	...
fi

if <condition> then
	command1
	command2
	...
else
	command1
	command2
	...
fi

Example:
$ cat > ispostive
#!/bin/sh
#
#Script to see whether argument is positive
#
if test $1 -gt 0
then
	echo "$1 number is positive"
else
	echo "$1 number is nExampleotive"
fi

## For loop
for { variable name } in { valuable list }
do
	command1
	command2
done

Example:
for i in 1 2 3 4 5
do
	echo $i
done

#for
for (( expr1; expr2; expr3 ))
do
	command1
	command2
done

Example: 
for (( i = 0 ; i <= 5; i++ )) # use (())
do
	echo $i
done

## While loop
while	[ condition ]
do
	command1
	command2
	command3
done

Example:
#!/bin/sh
echo "Nhap vao cac so can tinh tong, nhap so am de exit"
sum=0
read i
while [ $i -ge 0 ] # nếu i >= 0
do
sum=`expr $sum + $i`
read i # nhận giá trị từ người dùng
done
echo "Total: $sum."
