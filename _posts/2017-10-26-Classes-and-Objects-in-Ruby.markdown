---
layout: post
title:  "Classes and Objects in Ruby"
date:   2017-10-26 19:36:36 -0700
categories: Ruby
---

What's the difference between a `Class` and an `Object` in Ruby?

Classes are categories used to group objects such as Integer, String, TrueClass, Array, Hash, Symbol, etc. Objects are concrete instances of a class, they are pieces of data like `9`, `"strings"`, `true`, `[1, "hi", false]`  etc. with their own methods. Methods are the functions that define a behavior that is applied to the object's data such as sorting an array of integers or concatenating strings.

To define a class you need the `class` and `end` keywords and the name of the class should be an uppercase letter (use CamelCase convention if using more than one word to describe the class):

{% highlight ruby %}
class CommonPets
end
{% endhighlight %}

Classes tend to have characteristics and every class will define methods that are specific to the objects that belong in the class. Every time a new object is instantiated from a class, the new object will inherit all of the class methods.

{% highlight ruby %}
class CommonPets
  @breathe = true
end
{% endhighlight %}

Each instance (object) can have its own methods attached to itself

{% highlight ruby %}
class Cat < CommonPets
  def meow
    puts "Meow!"
  end
end
{% endhighlight %}

To create a new instance of Cat we can utilize the `new` method which is defined on the `Class` itself (which is also an `Object` and thus can have methods). The `new` method will create an instance of `Cat` and return it.
{% highlight ruby %}
myCat = Cat.new
# #<Cat:0x00007f9f070afc78> returns the name of the class and the unique internal object ID Ruby assigned
{% endhighlight %}

To verify that the new `Cat` instance is actually an instance of `Cat`:

{% highlight ruby %}
myCat.class
# => Cat

myCat.is_at?(Cat)
# => true
{% endhighlight %}



