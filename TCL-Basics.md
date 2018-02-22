## Variable

**Special variables**

- argc  - Refers to a number of command-line arguments.
- argv  - Refers to the list containing the command -line arguments.
- argv0 - Refers to the file name of the file being interpreted or the name by which we invoke the script.
- env   - Used for representing the array of elements that are environmental variables.
- tcl_version - Returns the current version of the Tcl interpreter.

```
puts $tcl_version
puts $env(PATH)
```

**Initializing variables**

```
set <variable_name> <variable_value>
```
```
Example:
set a 3
set name "abcd"
set price 12.2
```

**Returning a value of a variable**
```
set a
```

**Using value of variable**
```
set y $x
puts $y
```
**Using puts**
```
set x 10
set y 20
puts "value of x is $x"
puts "value of y is $y"
```
## Mathematical operations
**expr**
```
Example 1:
set x 10
set y 20
expr $x + $y
```
```
Example 2:
set x 10
set y 20
set z [expr $x + $y]
puts "result of addition: $z"
```
```
Example 3:
set radius 7
set pie [expr 22.0/7]
set area [expr $pie*$radius*$radius]
puts "Area of circle: $area"
```

## Conditional and Looping Statements

**if and if-else**
```
Example 1:
set x 10
if { $x < 50 } {
puts "x is less than 50"
}
```
```
Example 2:
if [ expr $x == 20 ] {
puts "x is equal to 20"
} else {
puts " x is not equal to 20"
}
```

**while loop**
```
Example 1:
set s 0
while { $s < 100 } {
puts $s
set s [expr $s+2]
}
```

**for loop**
```
Example 1:
for {set i 0} { $i < 10} { incr i} {
puts $i
}
```
**List**

List is nothing but a group of elements. A group of words either using double quotes or curly braces can be used to represent a simple list. 
```
set myVariable {red green blue}
puts [lindex $myVariable 2]
set myVariable "red green blue"
puts [lindex $myVariable 1]
```
**Associative arrays**

Associative arrays have an index (key) that is not necess arily an integer. It is generally a string that acts like key value pairs. 
```
Example 1:
set a(0) 10
set a(1) 30
puts $a(0)
```
```
Example 2:
set b {10,30}
puts $b(0)
```
```
Example 3:
set marks(english) 80
puts $marks(english)
set marks(mathematics) 90
puts $marks(mathematics)
```

**Size of arrays**
```
set languages(0) Tcl
set languages(1) "C Language"
puts  [array size languages]
```

**Indices of arrays**
```
set personA(Name) "Dave"
set personA(Age) 14
puts [array names personA]
```

## Procedure

```
proc fact { a } {
  set fact 1
  for {set i 1} {$i <= $a} {incr i} {
    set fact [expr $fact * $i]
  }
  puts $fact
}
# Calling procedure
fact 5
```

**Golabl variable in procedure**
```
set x 20
proc demo { } {
  global x
  set x 30
}
demo
puts $x
```
## File Handling

**File opening**
```
#open <file_name> <acc_type>
open one.txt r
```
 
**For assigning open file handle to variable**
```
set f_in [open one.txt r]  
```

**Syntax for writing in file**
```
puts <file_handle> <data|variable_value>
```
```
set f [open one.txt w]
puts $f "welcome to tcl"
close $f
```
**Reading file**
```
# gets <file_handle> <variable_value>
 
set f [open one.txt r]
gets $f data
 
puts $data
close $f
```
