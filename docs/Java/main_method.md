!!! Warning "Note"
    Site Under construction

    * [x] - Content - Friday OCT 3
    * [ ] - correctness
    * [ ] - grammar
    * [ ] - Improvemts
    * [ ] - Final tweaks

# The main method in Java

When running a java project. Java first needs an entry point.
The entry point is the `main()` method. The main method will have the following signature.

```java
public static void main(String[] args)
```

## Multiple classes and main methods
The main method can be defined in any class, usually public. There can be multiple classes with main method,However, only one main method will execute and that will be from the class from which run was executed.

## Static in main signature

The main method is kept as a static method so that it can be ran with calling an object of the class. And it also means that the main method is defined for the class and not associated with a particular object. Allowing main method to be called directly.