# Hello, World!

!!! Warning "Note"
    Site Under construction

    * [x] - Content - Friday OCT 2
    * [ ] - correctness
    * [ ] - grammar
    * [ ] - Improvemts
    * [ ] - Final tweaks

Hello world is the first thing we learn for any programing language. Following the tradition we write the Hello world program for Ruby.

Ruby has two commands for printing outputs to console.

- `print`
- `puts`
- `p`

## 1. `puts` and `print`

Lets take a look at syntax for the first two

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

## 2. More observations 

### interaction with arrays

`puts` and `print` has an interesting interaction with arrays

```rb
puts [1,2,3,nil]
```
```sh
$ 1
$ 2
$ 3
```
`puts` Outputted the elements of the array one by one in new line. Another interesting observation to add is that the last element of the array which is `nil` is ignored

!!! info 
    `nil` is similar to `Null` or `None` from other programing languages 

Now lets see what we get when we output an array using `print`

```rb
print [1,2,3,nil]
```

```
$ [1,2,3,nil]
```
`print` gives a string representation of array in a single line.

### Return type of `puts` and `print`

Next observation is regarding the return type of `puts` and `print`. puts always returns a `nil` while `print` returns a string.

## 3.The use of `p`

`p` is used mainly for debugging purposes as in it returns a raw output. Lets look at an example

```rb
p "Hello, World\n"
```
```
$ "Hello, World\n"
```
Here we see that `p` outputs a raw output including the new line escape charecter which is other wise hidden when using `puts` and `print`

## Reference 

* Jesus Castellos [Ruby Guides](https://www.rubyguides.com/2018/10/puts-vs-print/)
* Mike Danes [Youtube tutorial](https://www.youtube.com/watch?v=t_ispmWmdjY)
* Prof. Mark Keane Lecture [COMP47530](https://sisweb.ucd.ie/usis/!W_HU_MENU.P_PUBLISH?p_tag=MODULE&MODULE=COMP47530)