# Hello, World!

!!! Warning "Note"
    Site Under construction

    * [x] - Content - Friday NOV 6
    * [ ] - correctness
    * [ ] - grammar
    * [ ] - Improvemts
    * [ ] - Final tweaks

Ruby has some interesting concepts when it comes to variables. Like python Ruby variables are duck typed. This means ruby dynamically decides what the variable type is

Ruby has 4 different types of variables 



|                     | Naming                        | Scope                                    | Initialization                                         |
|---------------------|-------------------------------|------------------------------------------|--------------------------------------------------------|
| `Global Variable`   | Starts with $                 | Globally accesible                       | initialized with nil                                   |
| `Local Variablw`    | Starts with small letter or _ | Available only inside a block            | No initialization means ruby will think its a function |
| `Class variable`    | Starts with @ sign            | Only available in corresponding instance | initialized with nil                                   |
| `Instance variable` | Starts with @@ sign           | Scope limited to class                   | Need initializatiln else causes error                  |
    
    
## 1. Global Variable

Global variable like all program are variables accesible from everywhere in program. Global variables must be initialized with `$` and must be accessed with same symbol as well

``` rb

$var_x = 1
puts $var_x

def local_var
  puts "The is local variable #{$var_x}"
end
local_var
```

```
$ The is local variable 1

```
## 2. Local Variables

Local variables are identical to the python variables we use. The convention is to start with small letter or with _ .

```rb
char_name = "Sachin"
char_age = "25"
puts ("My name is #{char_name}. I am #{char_age} years old")
```

## 3.Instance variable

Requires the use of symbol `@`, This will be similar to the instance varibales in python always assocuated with a single instance

## 4. Class Variable

These variables have have to be initialized with `@@` symbol. Class varibale is associate with the full class. The following example will show how to use `instance` and `class` variables.


```rb
class Employee
  @@no_employees = 0
  def initialize(name)
    @employee_name = name
    @@no_employees+=1
  end

  def result
    puts "The name of the employee is #@employee_name"
    puts "The total number of Employees are #@@no_employees"
  end
end

x = Employee.new("Sachin")
x1 = Employee.new("Yu")
x2 = Employee.new("Freddi")
x.result
x1.result
x2.result
```
```
$ The name of the employee is Sachin
$ The total number of Employees are 3
$ The name of the employee is Yu
$ The total number of Employees are 3
$ The name of the employee is Freddie
$ The total number of Employees are 3
```


## Reference 

* Jesus Castellos [Ruby Guides](https://www.rubyguides.com/2018/10/puts-vs-print/)
* Mike Danes [Youtube tutorial](https://www.youtube.com/watch?v=t_ispmWmdjY)
* Prof. Mark Keane Lecture [COMP47530](https://sisweb.ucd.ie/usis/!W_HU_MENU.P_PUBLISH?p_tag=MODULE&MODULE=COMP47530)