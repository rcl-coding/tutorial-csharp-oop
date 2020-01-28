---
title: Lesson 3 - Inheritance
has_children: false
nav_order: 4
description: C# Inheritance
---

[![ad](../img/bootcamp.jpg)](https://rclapp.com/bootcamp.html)

****

# Inheritance

Inheritance allows you to extend the functionality of an existing class by creating a new class that derives from the inherited class.

- Add a 'Cylinder' class that inherits from the 'Circle' class as follows :

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
    
    // Add a Circle class
    public class Circle
    {
        public int Radius { get; set; }
    }
    // Add a Cylinder class that inherits from the Circle class
    public class Cylinder : Circle
    {
        public int Height { get; set; }
    }
}

```

The Circle class has a property named Radius of type integer. 

The Cylinder class inherits from the Circle class. We use the colon (:) to define the inheritance. 

The Cylinder class , because it inherits from the Circle class, will also have a property named Radius. 

- Write the following code to get the radius property (inherited) of the Cylinder :

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Get the radius property (inherited) for the Cylinder
            Cylinder myCylinder = new Cylinder();
            myCylinder.Radius = 5;
            myCylinder.Height = 12;

            Console.WriteLine($"The radius of the cylinder is {myCylinder.Radius}");
        }
    }
    
    public class Circle
    {
        public int Radius { get; set; }
    }

    public class Cylinder : Circle
    {
        public int Height { get; set; }
    }
}
```

- Run the application in the Console Window

Output in Console Window

```
The radius of the cylinder is 5
```

## Method Overrides

The override modifier is required to extend or modify the virtual implementation of an inherited method.

-  Add a virtual method in the Circle class. Override the virtual method in the Cylinder class as follows :

```csharp
    // Add a virtual method
    public class Circle
    {
        public int Radius { get; set; }

        public virtual decimal CalculateSurfaceArea()
        {
            return 2 * 3.14M * Radius;
        }
    }
    // Override the virtual method
    public class Cylinder : Circle
    {
        public int Height { get; set; }

        public override decimal CalculateSurfaceArea()
        {
            return (2 * 3.14M * Radius * Height) + (2 * 3.14M * Radius * Radius);
        }
    }
```

The Circle class has a virtual method called CalculateSurfaceArea that calculates the surface area of a circle. The 'virtual' keyword is used to declare that this method is a virtual method and can be overridden. 

The Cylinder class inherits from the Circle class, however, the function to calculate the area of a circle is different from the function to calculate the area of a cylinder. 

Therefore, in the Cylinder class, we can override the method to provide a function to calculate the surface area of a cylinder (as shown in the code). We use the keyword 'override' to override the virtual method.

- Write the following code to calculate the area of a cylinder

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Calculate area of a cylinder
            Cylinder myCylinder = new Cylinder();
            myCylinder.Radius = 2;
            myCylinder.Height = 3;
            decimal surfaceArea = myCylinder.CalculateSurfaceArea();

            Console.WriteLine($"The surface area of the cylinder is {surfaceArea}");
        }
    }

    public class Circle
    {
        public int Radius { get; set; }

        public virtual decimal CalculateSurfaceArea()
        {
            return 2 * 3.14M * Radius;
        }
    }

    public class Cylinder : Circle
    {
        public int Height { get; set; }

        public override decimal CalculateSurfaceArea()
        {
            return (2 * 3.14M * Radius * Height) + (2 * 3.14M * Radius * Radius);
        }
    }
}
```

- Run the application in the Console Window

Output in Console Window

```
The surface area of the cylinder is 62.80
```

****

[![ad](../img/online-mentoring.jpg)](https://rclapp.com/mentors.html)

****

<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
this.page.url = 'https://csharpoop.tutorial.rclapp.com/lessons/lesson3.html';
this.page.identifier = 'f04-03'; 
};
(function() { 
var d = document, s = d.createElement('script');
s.src = 'https://coding-skills-io.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>