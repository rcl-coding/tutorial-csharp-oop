---
title: Lesson 6 - Static Class
has_children: false
nav_order: 7
description: C# Static Class
---

[![ad](../img/bootcamp.jpg)](https://rclapp.com/bootcamp.html)

****

# Static Class

In static classes, you do not need to instantiate objects.

- Add a static class named Math

- Implement the static class as follows :

```java
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            // Implement the static class
            int x = 2;
            int y = 6;

            int sum = Math.Add(x, y);

            Console.WriteLine($"The sum of {x} and {y} is {sum}");
        }
    }

    // Add a static class
    public static class Math
    {
        public static int Add(int x, int y)
        {
            return x + y;
        }
    }
}
```

- Run the application in the Console Window

Output in Console Window

```
The sum of 2 and 6 is 8
```

Math is a static class, we use the keyword static to declare that the class is static. 

There is a static method named Add that adds two numbers. 

Since we do not need to instantiate an object, we can return the value from the Add method by simply using : Math.Add(x,y)

****

[![ad](../img/online-mentoring.jpg)](https://rclapp.com/mentors.html)

****

<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
this.page.url = 'https://csharpoop.tutorial.rclapp.com/lessons/lesson6.html';
this.page.identifier = 'a04-06'; 
};
(function() { 
var d = document, s = d.createElement('script');
s.src = 'https://coding-skills-io.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>