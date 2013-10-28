---
layout: post
title: "C# syntax highlighting example"
description: ""
category: ""
tags: []
---
{% include JB/setup %}

## Standard code

<pre><code class="language-csharp">
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

## Some code with contextual keywords

<pre><code class="language-csharp">
    /// &lt;summary>
    /// Some documentation
    /// &lt;/summary>
    partial class MyClass
    {
        public static SomeMethod(out int something){
            var query = from item in new[]{ "a", "b", "c" }
                        where item.Length > 0
                        orderby item
                        select item;
        }

        public IEnumerable<string> Iterator()
        {
            for (int i = 0; i < length; i++)
			{
                yield return i.ToString();
			}
        }
    }
</code></pre>
