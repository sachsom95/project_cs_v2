# Object Oriented Programing


!!! Warning "Note"
    Site Under construction

    * [ ] - Content - Friday OCT 3
    * [ ] - correctness
    * [ ] - grammar
    * [ ] - Improvemts
    * [ ] - Final tweaks


OOPS allows us to write programs in a way that its easy to write, easy to maintain, and easy to debug. The philosophy behind OOPS is that we should build a program that is focused around the problem we try to solve. For example if we are trying to create a pizza delivery system. In real life we have delivery man, map, the kitchen. All these can be defined as objects in our program and have them interact as seperate entities. These concepts will become much more clearer when we start to work on examples

## 1. Class
A class is a user defined  data type that we can create to for a particular problem we aim to solve. Example we have `String` class. A String class job is to store Strings and do manipulations. Similarly we can make our own classes which has some functionality. A class can be looked at as a template and we can create multiple instances of the class and we call them `objects`. 

!!! Info
    When programers are first taught what an object is. There will be random exaples thrown at them like car is an object etc. These examples will not make sense unless you know what an object is. Therefore its best to dive into an example

One thing to note is that each object that is created stores some information. The information inside the object can be modified without affecting the other objects.

## 2. Class in Action

### Problem statement

So lets say we are working on a map project. In this project we need to represent locations of any object including my current location. So what what are the informations we need to represent that? If we think about it we can define a persons location using two pieces of data, the latitude and longitude. So lets define a class that can hold this notion of a location.

```java

public class SimpleLocation
{   
    // member variables
    public double latitude;
    public double longitude;

    // contstructor
    public SimpleLocation(double lat, double lon)
    {
        this.latitude = lat;
        this.longitude = lon;
    }
    // method
    public double distance(SimpleLocation other)

    {
            // some implimentation logic 
    }


}

```






```java

public class LocationTester
{
    public static void main(String[] args)
    {

        SimpleLocation ucd = new SimpleLocation(32.9,-117.2);
        SimpleLocation dublin = new SimpleLocation(-12.0,-77.0);

        System.out.println(ucd.distance(dublin));

    }
}

```