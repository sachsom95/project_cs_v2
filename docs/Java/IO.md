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
