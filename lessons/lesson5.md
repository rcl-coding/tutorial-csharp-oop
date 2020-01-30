---
title: Lesson 5 - Abstract Class
has_children: false
nav_order: 6
description: C# Abstract Class
---

[![ad](../img/bootcamp.jpg)](https://rclapp.com/bootcamp.html)

****

# Abstract Class

An abstract class cannot be instantiated and can contain abstract and non-abstract members. Classes will inherit from an abstract class can extend its capabilities.

- Add an abstract class named MathBase

- Add a Adder class that inherits from the MathBase abstract class

- Add a Multiplier class that inherits from the MathBase abstract class

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello WOrld!");
        }
    }

    // Add an abstract class named MathBase
    public abstract class MathBase
    {
        public int X { get; set; }
        public int Y { get; set; }

        public MathBase(int x, int y)
        {
            X = x;
            Y = y;
        }

        public abstract int Execute();
    }
    // Add an Adder class that inherits from the MathBase abstract class
    public class Adder : MathBase
    {
        public Adder(int x, int y)
            : base(x, y)
        {
        }

        public override int Execute()
        {
            return X + Y;
        }
    }
    // Add a Multiplier class that inherits from the MathBase abstract class
    public class Multiplier : MathBase
    {
        public Multiplier(int x, int y)
            : base(x, y)
        {
        }

        public override int Execute()
        {
            return X * Y;
        }
    }
}
```

MathBase is an abstract class. The keyword abstract is used to declare an abstract class. The MathBase class has an abstract method named Execute that can be overridden by a class that inherits from it. 

There are also two non-abstract properties named X and Y, that will be used to represent two integer numbers. 

The Adder class inherits from the MathBase class and provides an implementation for the Execute method (it adds Y and Y) by overriding the abstract method. 

The Adder class has a constructor that initializes the X and Y properties that it inherits from the MathBase class.

The Multiplier class inherits from the MathBase abstract class and multiplies the two numbers.

- Write the following code to implement the Adder and Multiplier classes :

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Implement the Adder and Multiplier classes
            int x = 2;
            int y = 6;

            MathBase myAdder = new Adder(x, y);
            int sum = myAdder.Execute();

            MathBase myMultiplier = new Multiplier(x, y);
            int product = myMultiplier.Execute();

            Console.WriteLine($"The sum of {x} and {y} is {sum}");
            Console.WriteLine($"The product of {x} and {y} is {product}");
        }
    }

    public abstract class MathBase
    {
        public int X { get; set; }
        public int Y { get; set; }

        public MathBase(int x, int y)
        {
            X = x;
            Y = y;
        }

        public abstract int Execute();
    }

    public class Adder : MathBase
    {
        public Adder(int x, int y)
            : base(x, y)
        {
        }

        public override int Execute()
        {
            return X + Y;
        }
    }

    public class Multiplier : MathBase
    {
        public Multiplier(int x, int y)
            : base(x, y)
        {
        }

        public override int Execute()
        {
            return X * Y;
        }
    }
}
```

- Run the application in the Console Window

Output in Console Window

```
The sum of 2 and 6 is 8
The product of 2 and 6 is 12
```

****

[![ad](../img/online-mentoring.jpg)](https://rclapp.com/mentors.html)

****

<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
this.page.url = 'https://csharpoop.tutorial.rclapp.com/lessons/lesson5.html';
this.page.identifier = 'a04-05'; 
};
(function() { 
var d = document, s = d.createElement('script');
s.src = 'https://coding-skills-io.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>