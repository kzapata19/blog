---
layout: post
title:  "JavaScript and Ruby Comparison"
date:   2017-10-26 19:36:36 -0700
categories: jekyll update
---

As I worked through the Ruby Koans this week, some of the surface level differences I've noticed between JavaScript and Ruby include:

#### `typeof` and `class`
To find the value type of an object in JavaScript, `typeof <targetObject>`
With Ruby, this can be achieved by appending `.class` to the target_object

#### Functions and Methods
Functions in JavaScript are the same as Ruby's methods. The syntax, however, is different:

```javascript
var sayMyName = name => `Greetings, ${name}!`
```

In Ruby, the same logic is written as:

{% highlight ruby %}
def sayMyName(name)
  puts "Greetings, #{name}!"
end
{% endhighlight %}

#### `===` and `==`
JavaScript's `===` does a `typeof` and value comparison. The `===` in Ruby is the case subsumption operator. It's a boolean operator that determines whether the object on the right of the operator belongs to the set described by the object on the right. [This] top rated stackoverflow response explains Ruby's `===` very clearly.

In JavaScript, the `==` performs a 'typeof' comparison only. Whereas with Ruby, the `==` performs a value comparison

#### Falsy Values

One notable difference between JavSCript and Ruby is the falsy values. Unlike JavaScript, everything except `nil` (similar to JavaScript's `undefined`) and `false` are truthy values in Ruby.

In JavaScript, `false` (boolean not the string `"false"`), `0`, `""`, `''`, `undefined`, `null`, and `NaN`.


[This]: https://stackoverflow.com/questions/4467538/what-does-the-operator-do-in-ruby