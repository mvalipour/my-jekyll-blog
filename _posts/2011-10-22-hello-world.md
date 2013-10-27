---
layout: post
categories : [lessons, hello]
tags : [intro, jekyll]
---
{% include JB/setup %}


A "Hello world" program is a computer program that outputs "Hello, world" on a display device. Because it is typically one of the simplest programs possible in most programming languages, it is by tradition often used to illustrate to beginners the most basic syntax of a programming language. It is mostly used to verify that a language or system is operating correctly.

<pre><code class="language-css">p { color: red }</code></pre>

<!--more-->

###Variations

<pre><code class='language-csharp'>
using System;
class Person
{
    private string myName ="N/A";
    private int myAge = 0;

    // Declare a Name property of type string:
    public string Name
    {
        get 
        {
           return myName; 
        }
        set 
        {
           myName = value; 
        }
    }

    // Declare an Age property of type int:
    public int Age
    {
        get 
        { 
           return myAge; 
        }
        set 
        { 
           myAge = value; 
        }
    }

    public override string ToString()
    {
        return "Name = " + Name + ", Age = " + Age;
    }

    public static void Main()
    {
        Console.WriteLine("Simple Properties");

        // Create a new Person object:
        Person person = new Person();

        // Print out the name and the age associated with the person:
        Console.WriteLine("Person details - {0}", person);

        // Set some values on the person object:
        person.Name = "Joe";
        person.Age = 99;
        Console.WriteLine("Person details - {0}", person);

        // Increment the Age property:
        person.Age += 1;
        Console.WriteLine("Person details - {0}", person);
    }
}
</code></pre>

There are many variations on the punctuation and casing of the phrase. Variations include the presence or absence of the comma and exclamation mark, and the capitalization of the 'H', both the 'H' and the 'W', or neither. Some languages are forced to implement different forms, such as "HELLO WORLD!", on systems that support only capital letters, while many "hello world" programs in esoteric languages print out a slightly modified string. For example, the first non-trivial Malbolge program printed "HEllO WORld", this having been determined to be good enough.

There are variations in spirit, as well. Functional programming languages, like Lisp, ML and Haskell, tend to substitute a factorial program for Hello World, as functional programming emphasizes recursive techniques, whereas the original examples emphasize I/O, which violates the spirit of pure functional programming by producing side effects.

The Debian and Ubuntu Linux distributions provide the "hello world" program through the apt packaging system; this allows users to simply type "apt-get install hello" for the program to be installed, along with any software dependencies. While of itself useless, it serves as a sanity check and a simple example to newcomers of how to install a package. It is significantly more useful for developers, however, as it provides an example of how to create a .deb package, either traditionally or using debhelper, and the version of hello used, GNU hello, serves as an example of how to write a GNU program.[7]

###Examples

The Hello World program can be executed in many different programming languages, and in many different ways. The simplest ways are generally to just create a print line, or a String containing the words "Hello World!", however, one can use substrings and many other variations of programming in order to execute the Hello World program creation. For example - in Java, the simplest form would most likely look something like this: