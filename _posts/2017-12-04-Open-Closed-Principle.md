---
layout: post
title:  "Open-Closed Principle (OCP)"
date:   2017-12-04 19:36:36 -0700
categories: Uncle Bob, SOLID, software, OO, design
---

"Open for Extension, Closed for Modification"

The "O" in Uncle Bob's SOLID principles. The concept seems really easy to understand but it's a bit more challenging to implement when writing code.

We can achieve this goal by aiming to create modular code that will make it possible for us to change the behavior o the app without making changes to the classes themselves. Some of the *code smells* include `if else` statements and lengthy `switch` cases. One way to solve this issue is to use the *strategy pattern*. According to [Wikipedia](https://en.wikipedia.org/wiki/Strategy_pattern)

> The strategy pattern is a behavior software design pattern that enables selecting an algorithm at runtime. The strategy pattern:
> * defines a family of algorithms
> * encapsulates each algorithm, and
> * makes the algorithms interchangeable within that family

Let's take a look at an example. We start off with the following classes that violate OCP.

{% highlight ruby %}
class Circle

  attr_reader :radius

  def initialize(radius)
    @radius = radius
  end

end

class Square

  attr_reader :length

  def initialize(length)
    @length = length
  end

end

class CalculateArea

  attr_reader :shapes

  def initialize(shapes_array)
    @shapes = shapes_array
  end

  def add
    sum = 0
    @shapes.each do |shape|
      if shape.class.name == "Square"
        sum = sum + (shape.length ** 2)
      else
        sum = sum + (Math::PI * (shape.radius**2))
      end
    end
    sum
  end

end

{% endhighlight %}

We have a `Square` class with a `length` attribute and a `Circle` class with a `radius` attribute. The `CalculateArea` does what its name suggests by checking the shape's class name to perform the appropriate calculation.

The issue with `CalculateArea` is that if we were to add another shape (for example a Triangle), we would need to extend the if-else statement to check for a Triangle. This violates the Open-Close Principle.

Let's refactor using the *strategy pattern*. We'll extract the area calculation for each shape out of `CalculateArea` and place it inside each object's class as such:

{% highlight ruby %}
class Circle

  attr_reader :radius

  def initialize(radius)
    @radius = radius
  end

  def calculate_area
    Math::PI * (radius**2)
  end

end

class Square

  attr_reader :length

  def initialize(length)
    @length = length
  end

  def calculate_area
    length ** 2
  end

end

class CalculateArea

  attr_reader :shapes

  def initialize(shapes_array)
    @shapes = shapes_array
  end

  def add
    @shapes.inject(0) do |sum, shape|
      sum = sum + shape.calculate_area
    end
  end

end

{% endhighlight %}

Now we can create a Triangle class if we wanted and pass it along to `CalculateArea` to be added to the total area sum.

The main idea of the *strategy pattern* is to define the set of objects (strategies) which solve the same problem (calculating the area of a specific shape) in a different way based on different conditions. In our case, we calculate the area of the shape inside it's class instead of performing the calculation inside `CalculateArea`. Also now that we calculate the area inside each shape's class, we might want to rename `CalculateArea` to `CalculateAreaSum` or something else that reflects it's new responsibility.

