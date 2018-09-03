
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
