---
title: Lesson 2 - Method
has_children: false
nav_order: 3
description: C# Methods
---
[![ad](../img/bootcamp.jpg)](https://rclapp.com/bootcamp.html)

****

# Methods

A method carries out a function within a class.

- In the Square class add a method to calculate the area of the square :

```java
    public class Square
    {
        public int Side { get; set; }

        public Square(int side)
        {
            Side = side;
        }

        // Add method to calculate area
        public int CalculateArea()
        {
            return Side * Side;
        }
    }
```

- Use the method to calculate the area of a square as follows :

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Use the method to calculate area
            Square mySquare = new Square(4);
            int area = mySquare.CalculateArea();

            Console.WriteLine($"The area of a square with side {mySquare.Side} is {area}");
        }
    }

    public class Square
    {
        public int Side { get; set; }

        public Square(int side)
        {
            Side = side;
        }

        public int CalculateArea()
        {
            return Side * Side;
        }
    }
}
```

- Run the application in the Console Window

Output in Console Window

```
The area of a square with side 4 is 16
```

In the Square class, we have a method named CalculateArea(), this method does not take any arguments and returns an integer. 

The method uses the Side property to calculate the area of the square. The method **returns** an integer value for the area (Side * Side).

## Method Overloads

A class can have two or more methods with the same name but take different number and types of arguments and carry out functions differently. 

This is called **method overloading**.

- Create a class named 'Shape' with method overloads as follows :

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine($"Hello World!");
        }
    }

    // Create a Shape class with method overloads
    public class Shape
    {
        public decimal CalculateArea(int Radius)
        {
            return 3.14M * Radius * Radius;
        }

        public int CalculateArea(int Length, int Breadth)
        {
            return Length * Breadth;
        }
    }
}
```

- Use the method overloads to calculate area of a circle and rectangle as follows :

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Calculate area of circle
            Shape myCircle = new Shape();
            int radius = 2;
            decimal areaCircle = myCircle.CalculateArea(radius);

            // Calculate area of rectangle
            Shape myRectangle = new Shape();
            int length = 4;
            int breadth = 2;
            int areaRectangle = myRectangle.CalculateArea(length, breadth);

            Console.WriteLine($"The area of a circle with radius {radius} is {areaCircle}");
            Console.WriteLine($"The area of a rectangle with length {length} and breadth {breadth} is {areaRectangle}");
        }
    }

    public class Shape
    {
        public decimal CalculateArea(int Radius)
        {
            return 3.14M * Radius * Radius;
        }

        public int CalculateArea(int Length, int Breadth)
        {
            return Length * Breadth;
        }
    }
}
```

- Run the application in the Console Window

```
The area of a circle with radius 2 is 12.56
The area of a rectangle with length 4 and breadth 2 is 8
```

Output in Console Window

In the Shape class, there are two methods called CalculateArea , but one calculates the a area of a circle and the other calculates the area of a rectangle. 

The first method takes one argument, of type integer, for the radius and returns an area, of type decimal, for the circle (in, 3.14M, M shows that this is a decimal number). 

The second method takes two arguments, of type integer, for the length and breadth and returns the area, of type integer, for the rectangle. 

The CalculateArea method has two overloads.

****

[![ad](../img/online-mentoring.jpg)](https://rclapp.com/mentors.html)

****

<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
this.page.url = 'https://csharpoop.tutorial.rclapp.com/lessons/lesson2.html';
this.page.identifier = 'a04-02'; 
};
(function() { 
var d = document, s = d.createElement('script');
s.src = 'https://coding-skills-io.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
