
# About shell in linux
```
#!/bin/bash
echo "hello world"
```
## Execute shell script
```
–  bash hello.sh
–  sh hello.sh
–  ./hello.sh
```

## If condition
```
if <condition> then
	command1
	command2
	...
fi
```
```
if <condition> then
	command1
	command2
	...
else
	command1
	command2
	...
fi
```
Multi condition
```
if condition
then
           condition is zero (true - 0)
           execute all commands up to elif statement
elif condition1 
then
           condition1 is zero (true - 0)
           execute all commands up to elif statement  
elif condition2
then
           condition2 is zero (true - 0)
           execute all commands up to elif statement          
else
           None of the above condtion,condtion1,condtion2 are true (i.e. 
           all of the above nonzero or false)
           execute all commands up to fi
fi
```

Example:
```
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
```

```
#!/bin/sh
# Script to test if..elif...else
#
if [ $1 -gt 0 ]; then
  echo "$1 is positive"
elif [ $1 -lt 0 ]
then
  echo "$1 is negative"
elif [ $1 -eq 0 ]
then
  echo "$1 is zero"
else
  echo "Opps! $1 is not number, give number"
fi
```

### Case
```
case  $variable-name  in
	pattern1)   command
				...
				..
				command;;
	pattern2)   command
				...
				..
				command;;
	patternN)   command
				...
				..
				command;;
	*)			command
				...
				..
				command;;
esac
```
Example:
```
# if no vehicle name is given
# i.e. -z $1 is defined and it is NULL
#
# if no command line arg

if [ -z $1 ]
then
  rental="*** Unknown vehicle ***"
elif [ -n $1 ]
then
# otherwise make first arg as rental
  rental=$1
fi

case $rental in
   "car") echo "For $rental Rs.20 per k/m";;
   "van") echo "For $rental Rs.10 per k/m";;
   "jeep") echo "For $rental Rs.5 per k/m";;
   "bicycle") echo "For $rental 20 paisa per k/m";;
   *) echo "Sorry, I can not gat a $rental for you";;
esac
```

## For loop
```
for { variable name } in { valuable list }
do
	command1
	command2
done
```

Example:
```
for i in 1 2 3 4 5
do
	echo $i
done
```

#for
```
for (( expr1; expr2; expr3 ))
do
	command1
	command2
done
```

Example: 
```
for (( i = 0 ; i <= 5; i++ )) # use (())
do
	echo $i
done
```

## While loop
```
while	[ condition ]
do
	command1
	command2
	command3
done
```

Example:
```
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
```

## Test command
```test``` or ```[ expr ]``` works with
1.Integer ( Number without decimal point)
2.File types
3.Character strings

```
Operator Meaning 			Normal		For test statement 	For [ expr ] statement with if command
-eq 	is equal to 			5 == 6 		if test 5 -eq 6 	if [ 5 -eq 6 ]
-ne 	is not equal to 		5 != 6 		if test 5 -ne 6 	if [ 5 -ne 6 ]
-lt 	is less than 			5 < 6 		if test 5 -lt 6 	if [ 5 -lt 6 ]
-le 	is less than or equal to 	5 <= 6 		if test 5 -le 6 	if [ 5 -le 6 ]
-gt 	is greater than 		5 > 6 		if test 5 -gt 6 	if [ 5 -gt 6 ]
-ge 	is greater than or equal to 	5 >= 6 		if test 5 -ge 6 	if [ 5 -ge 6 ]
```

### String Comparisons
```
Operator 		Meaning
string1 = string2 	string1 is equal to string2
string1 != string2 	string1 is NOT equal to string2
string1 		string1 is NOT NULL or not defined
-n string1 		string1 is NOT NULL and does exist
-z string1 		string1 is NULL and does exist
```

### File Comparisons
```
Test 		Meaning
-s file 	Non empty file
-f file 	Is File exist or normal file and not a directory
-d dir 		Is Directory exist and not a file
-w file 	Is writeable file
-r file 	Is read-only file
-x file 	Is file is executable.
```
### Logic Operator
```
Operator 			Meaning
! expression 			Logical NOT
expression1 -a expression2 	Logical AND
expression1 -o expression2 	Logical OR
```
**Rule of thumb:** Use ```-a``` and ```-o``` inside square brackets, ```&&``` and ```||``` outside.

### Special variable
```
$?: Exit status (0 - if previous command is successful, !0 - command is not successful or some sort of error executing command/shell script.)
$#: Number of parameter parse to shell script
$*, $@: All arguments to shell
$$: PID of shell
$!: PID of last started background process (started with &)
```

