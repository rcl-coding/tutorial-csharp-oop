---
title: Lesson 1 - Class and Object
has_children: false
nav_order: 2
description: C# Classes and Objects
---
[![ad](../img/bootcamp.jpg)](https://rclapp.com/bootcamp.html)

****

# Classes and Objects

**Classes** and **Objects** form the basis of object oriented programming.

## Class

A **class** is the blueprint from which individual objects are created.

- Create a class as named Square :

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }

    // Create a class named Square
    public class Square
    {
        public int Side { get; set; }
    }
}
```

In the code above, we declare a class called 'Square'. 

The word 'public' is an **accessor**, this class can be accessed by other classes. 

In the Square class, we declare a public **property** named 'Side' that is an integer.

## Object

An object is an instance of a class.

- Create two objects (smallSquare and bigSquare) as follows :

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create an object named smallSquare
            Square smallSquare = new Square();
            smallSquare.Side = 1;

            // Create an object named bigSquare
            Square bigSquare = new Square();
            bigSquare.Side = 600;

            Console.WriteLine($"The length of the Side for the bigSquare is {bigSquare.Side}");
        }
    }

    public class Square
    {
        public int Side { get; set; }
    }
}
```

- Run the application in the Console Window

Output in Console Window

```
The length of the Side for the bigSquare is 600
```

Above, we have a class named 'Square'. 

From that class, we **instantiate** two objects , one called 'smallSquare' and the other called 'bigSquare'. We use the **new** keyword to instantiate an object. 

We can set the properties of objects by using the dot (.) operator, for instance, we set the Side property of the small square to 1 by writing **smallSquare.Side = 1**.

If we want to get the property of an object we also use the dot (.) operator. For instance, to get the Side of the bigSquare we write : **bigSquare.Side**.

## Constructors

Constructors set the initial values of properties when a class in instantiated.

- Add a constructor in the Square class as follows :

```java
public class Square
{
    public int Side { get; set; }

    //Add a constructor
    public Square(int side)
    {
        Side = side;
    }
}
```

- Use the constructor to set the value of the 'Side' property as follows :

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Assign the value of the Side property with the constructor
            Square mySquare = new Square(4);

            Console.WriteLine($"The length of the Side for the mySquare object is {mySquare.Side}");
        }
    }

    public class Square
    {
        public int Side { get; set; }

        public Square(int side)
        {
            Side = side;
        }
    }
}

```

- Run the application in the Console Window

Output in Console Window

```
The length of the Side for the mySquare object is 4
```

In the Square class, we have a **constructor**. The constructor has the same name as the class. 

The constructor takes an integer parameter named 'side'. When the class is instantiated, the constructor runs first, and sets the Side property to the value (or **argument**) we provide to the parameter.

We instantiate an object named 'mySquare; and pass in an argument of 4 to the constructor. The constructor, will inturn, set the Side property to 4.

****

# Bob Tabor Videos

****

> NOTE - These videos are a little dated, Visual Studio 2013/2015 is being used here. But the principles are basically the same.

*****

## Understanding Data Types and Variables

<div style="position: relative;overflow: hidden;padding-top: 56.25%;">
<iframe src="https://channel9.msdn.com/Series/CSharp-Fundamentals-for-Absolute-Beginners/Understanding-Classes/player" style="position: absolute; top: 0;left: 0; width: 100%; height: 100%;border: 0" allowFullScreen frameBorder="0" title="Understanding Classes - Microsoft Channel 9 Video"></iframe>
</div>

****

[![ad](../img/online-mentoring.jpg)](https://rclapp.com/mentors.html)

****

<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
this.page.url = 'https://csharpoop.tutorial.rclapp.com/lessons/lesson1.html';
this.page.identifier = 'a04-01'; 
};
(function() { 
var d = document, s = d.createElement('script');
s.src = 'https://coding-skills-io.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>



