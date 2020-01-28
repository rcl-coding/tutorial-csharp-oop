---
title: Lesson 4 - Interface
has_children: false
nav_order: 5
description: C# Interface
---

[![ad](../img/bootcamp.jpg)](https://rclapp.com/bootcamp.html)

****

# Interfaces

An interface contains only the signatures of methods. A class that inherits from the interface must implement the members of the interface.

- Add an interface named IShape

- Add a class named Rectangle that inherits from the IShape interface

```csharp
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
    // Add an interface
    public interface IShape
    {
        int Area();
    }
    // Add a class that inherits from the interface
    public class Rectangle : IShape
    {
        public int Length { get; set; }
        public int Breadth { get; set; }

        public Rectangle(int length, int breadth)
        {
            Length = length;
            Breadth = breadth;
        }

        public int Area()
        {
            return Length * Breadth;
        }
    }
}
```

IShape is an interface that has a method signature named Area that should return an integer. 

The class Rectangle inherits from the IShape interface, and therefore, must implement a method named Area. 

The Rectangle class has Length and Breadth properties and a constructor to initialize these properties, in addition, it has an implementation for the Area method as shown in the code above.

- Write code to use the interface as follows :

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Use the interface
            IShape myRectangle = new Rectangle(4, 2);
            int area = myRectangle.Area();

            Console.WriteLine($"The area of the rectangle is {area}");
        }
    }

    public interface IShape
    {
        int Area();
    }

    public class Rectangle : IShape
    {
        public int Length { get; set; }
        public int Breadth { get; set; }

        public Rectangle(int length, int breadth)
        {
            Length = length;
            Breadth = breadth;
        }

        public int Area()
        {
            return Length * Breadth;
        }
    }
}
```

- Run the application in the Console Window

Output in Console Window

```
The area of the rectangle is 8
```

- Add an interface named IShape

- Add a Rectangle class that inherits from the IShape interface

- Add a Solid class that takes a IShape parameter in its constructor

## Using an interface in a constructor

The following example illustrates how we can use an interface in a constructor of a class.

This pattern is important for **dependency injection** and the **dependency inversion principle**.

```csharp
    // Add an IShape interface
    public interface IShape
    {
        int Area();
    }
    // Add a Rectangle class that inherits from the IShape interface
    public class Rectangle : IShape
    {
        public int Length { get; set; }
        public int Breadth { get; set; }

        public Rectangle(int length, int breadth)
        {
            Length = length;
            Breadth = breadth;
        }

        public int Area()
        {
            return Length * Breadth;
        }
    }
    // Add a Solid class that takes an IShape in its constructor
    public class Solid
    {
        public IShape Shape { get; set; }
        public int Height { get; set; }

        public Solid(IShape shape, int height)
        {
            Shape = shape;
            Height = height;
        }

        public int CalculateVolume()
        {
            return Shape.Area() * Height;
        }
```

The Solid class has a property called Height. It also has a property named Shape of type IShape (interface). 

The Solid class takes an IShape parameter in its constructor whit is uses to set the Shape property.

Since IShape has a method for Area, we could use that in the Solid class to define a method to calculate the volume , i.e. Shape.Area() * Height.

- Write the following code to calculate the volume if a cuboid :

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Claculate the volume of a cuboid
            IShape myRectangle = new Rectangle(4, 2);
            Solid myCuboid = new Solid(myRectangle, 3);
            int volume = myCuboid.CalculateVolume();

            Console.WriteLine($"The volume of the cuboid is {volume}");
        }
    }

    public interface IShape
    {
        int Area();
    }

    public class Rectangle : IShape
    {
        public int Length { get; set; }
        public int Breadth { get; set; }

        public Rectangle(int length, int breadth)
        {
            Length = length;
            Breadth = breadth;
        }

        public int Area()
        {
            return Length * Breadth;
        }
    }

    public class Solid
    {
        public IShape Shape { get; set; }
        public int Height { get; set; }

        public Solid(IShape shape, int height)
        {
            Shape = shape;
            Height = height;
        }

        public int CalculateVolume()
        {
            return Shape.Area() * Height;
        }
    }
}
```

- Run the application in the Console Window

Output in Console Window

```
The volume of the cuboid is 24
```

****

[![ad](../img/online-mentoring.jpg)](https://rclapp.com/mentors.html)

****

<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
this.page.url = 'https://csharpoop.tutorial.rclapp.com/lessons/lesson4.html';
this.page.identifier = 'f04-04'; 
};
(function() { 
var d = document, s = d.createElement('script');
s.src = 'https://coding-skills-io.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>