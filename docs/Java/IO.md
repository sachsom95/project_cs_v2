# Java IO read and write


!!! Warning "Note"
    Site Under construction

    * [ ] - Content - Friday May 2
    * [ ] - correctness
    * [ ] - grammar
    * [ ] - Improvemts
    * [ ] - Final tweaks



Java I/O is pretty big however it seems to follow a certain pattern therfore once we get the basics down the interfaces are all same. There are two main systems.

!!! info
    The IO is in java.io package

"IO System"

    * byte I/O
    * charecter I/O


Now what is byte IO and charecter IO?

Byte IO is basicallty the lowest form of input where the program accepts data in the form of 8 bits. This means we can transfer audio, video or any form of data.

The charecter stream is used to accept data in the form of 16 bit unicode. This is useful for accepting only charecter data, However, it is useful for internationalizing data



## 1. Charecter Stream

For now we will focus on the charecter stream as its more important from interview point of view though. We will discuss byte stream.

Byte stream has two abstract classes `InputStream` and `OutputStream` both have large number of classes which we can use. But we will focus on Charecter stream class

![charecter stream class]("images/io/char_stream.png")

If we look the most important will be 

    * BufferedReader
    * FileReader
    * InputStreamReader

We will need to create a BufferedReader for any type of inputs. Now if we are accepting data from the console it is from `System.in` which is already in java.lang and is Public Static final so we can call it anywhere.

## Example 1 Read Character from console

So lets start reading data from console 


```java

import java.io.*;
public class ReadFile {


    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        try {
            System.out.println("Enter number");
            int num = br.read();
            System.out.println((char)num);
            br.mark(1);
        }catch(IOException e){
            System.out.println("put an number bud");
        }   
    }
}
```

So couple of things to notice. First we make a BuffereReader this has to take input from `System.in` but that is in bytes this can be converted using a `InputStreamReader` therfore we use that.

The I/O all can throw `IOException`.

## Important observation

consider the following example

```java

import java.io.*;
public class ReadFile {


    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        try {
            System.out.println("Enter number");
            int num = br.read();
            System.out.println((char)num);
            br.mark(1);
        }catch(IOException e){
            System.out.println("put an number bud");
        }
        try{
            System.out.println("Enter a string");
            String x = br.readLine();
            System.out.println(x);
        }catch(IOException e){
            System.out.println("Illegal stuff mate");
        }
    }
}

```
here we have used a readLine() function after read() this will not work as expected because when we do a read(). The charecter which we entered is accepted but before that we need to press enter which adds EOF to the stream. So next time when we do a readLine() it will take the EOF and stop the read process. Therfore consider how the buffer takes in data.

## Numeric Wrappers

When we use character stream we will need to use the type Wrappers to convert data from one form to other. The type wrappers are Double, Float, Long, Integer, Short, Byte, Character, and Boolean.

So we can accept data in String format and convert to corresponding internal format we want.

for example if we need to convert to Integer we can do `Integer.parseInt(x)`

!!! info 
     why not use type cast?
     Type casting can only be done with compatible types like from double to int and between primitive types.
     String is not a primitive but an object therfore we need to do casting by fucntions associated with the given 
     object. "034" -> does not make sense hence we use Integer.ParseInt()



