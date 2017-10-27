---
layout: post
title:  "Classes and Objects in Ruby"
date:   2017-10-26 19:36:36 -0700
categories: jekyll update
---

What's the difference between a `Class` and an `Object` in Ruby?

Objects are pieces of data like `9`, `"strings"`, `true`, `[1, "hi", false]`  etc. with their own methods. Methods are the functions that define a behavior that is applied to the object's data such as sorting an array of integers or concatenating strings. Classes are categories used to group these pieces of data such as Integer, String, TrueClass, Array, Hash, Symbol, etc.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
