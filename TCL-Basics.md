**variables**

```
Variables in TCL:
set <variable_name> <variable_value>
```
```
Example:
set a 3
set name "abcd"
set price 12.2
```

** Returning a value of a variable**
```
set a
```

**Using value of variable**
```
set y $x
puts $y
```
# Using puts
set x 10
set y 20
puts "value of x is $x"
puts "value of y is $y"

# expr
Example 1:
set x 10
set y 20
expr $x + $y

Example 2:
set x 10
set y 20
set z [expr $x + $y]
puts "result of addition: $z"

Example 3:
set radius 7
set pie [expr 22.0/7]
set area [expr $pie*$radius*$radius]
puts "Area of circle: $area"

B. Conditional and Looping Statements

# if-else
Example 1:
set x 10
if { $x < 50 } {
puts "x is less than 50"
}
  
if [ expr $x == 20 ] {
puts "x is equal to 20"
} else {
puts " x is not equal to 20"
}

# while loop
Example 1:
set s 0
while { $s < 100 } {
puts $s
set s [expr $s+2]
}

# for loop
Example 1:
for {set i 0} { $i < 10} { incr i} {
puts $i
}

C. Array

# array
Example 1:
set a(0) 10
set a(1) 30
puts $a(0)
#Another Way
array set b {10,30}
puts $b(0)

D. Procedure

# Procedure
proc fact { a } {
  set fact 1
  for {set i 1} {$i <= $a} {incr i} {
    set fact [expr $fact * $i]
  }
  puts $fact
}
# Calling procedure
fact 5

# Golabl variable in procedure
Example 1:
set x 20
proc demo { } {
  global x
  set x 30
}
demo
puts $x

E. File Handling

# For opening file
# open <file_name> <acc_type>
open one.txt r
 
# For assigning open file handle to variable.
set f_in [open one.txt r]  

# Syntax for writing in file.
puts <file_handle> <data|variable_value>
 
set f [open one.txt w]
puts $f "welcome to tcl"
 
close $f

# Reading file
# Syntax for reading from file.
# gets <file_handle> <variable_value>
 
set f [open one.txt r]
gets $f data
 
puts $data
close $f
