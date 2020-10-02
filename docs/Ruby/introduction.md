# Hello, World!

!!! Warning "Note"
    Site Under construction - Friday OCT 2

Hello world is the first thing we learn for any programing language. Following the tradition we write the Hello world program for Ruby.

Ruby has two commands for printing outputs to console.

- `print`
- `puts`

Lets take a look at syntax for both of them

``` ruby

print "Hello, World!"
```
```
$ Hello, World!

```
This is fairly straight forward and simple.
The `print` command followed by string.
Now lets look at the syntax for `puts`.

```rb
puts "Hello, World!"
```
```
$ Hello, World!
```
Both seems to give same output. Inorder to find the difference between `print` and `puts` we need to run them together.

```rb

puts "Ruby is"
puts "Nice!"

print "Ruby is"
print " Nice!"

```
```sh

$ Ruby is
$ Nice!
$ Ruby is Nice!
```
Notice the difference. We see that when we used `puts` everything gets printed in different lines while for `print` all the output will be in same line.

!!! info
    
    This is analogus to `System.out.prinln()` and `System.out.print()` in java.

