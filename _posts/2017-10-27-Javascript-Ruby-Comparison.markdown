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

#### Naming Conventions

##### Ruby: identifier that starts with
- a capital letter is a constant, usually with all uppercase letters (NOTE: method names may start with a capital letter too!). Class and module names are constants and by convention use upper camel case. Constants should not be defined inside a method, normally in a class or module.
- `$` is a global variable
- `@` is an instance variable (declared within an object, always belongs to whatever object `self` references)
- `@@` is a class variable (declared inside a class, it's shared among all objects within that class)
NOTE:
- variables do not need to be declared, the name itself will denote the scope (local, global, instance, etc.)
- local variable (declared inside an object) is made up of a lowercase letter or underscore followed by any combination of upper/lowercase letter, underscores, and numbers
- method names are also allowed to include `?`, `!`, `=` as name suffixes


##### JavaScript:
- variable declarations should always start with `var` to avoid declaring them as global variables (avoids conflicts from using a variable name across different fuxs and other global variable declared by 3rd party code)
- constructor fx startig with `new` should start with a capital letter (ex: ` var new_person = new Person())
- methods/fxs should always start with a lowercase letter
- follow camel case convention for methods/fx and upper camel case for constructors
- variables with multiple words should use underscore between words
- use leading underscore to visually separate private from public methods (NOTE: this convention does not create a private method)

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
JavaScript's `===` does a `typeof` and value comparison. The `===` in Ruby is the case subsumption operator. It's a boolean operator that determines whether the object on the right of the operator belongs to the set described by the object on the right. [This] stackoverflow page explains Ruby's `===` very clearly.

In JavaScript, the `==` performs a 'typeof' comparison only. Whereas with Ruby, the `==` performs a value comparison

#### Falsy Values

One notable difference between JavSCript and Ruby is the falsy values. Unlike JavaScript, everything except `nil` (similar to JavaScript's `undefined`) and `false` are truthy values in Ruby.

In JavaScript, `false` (boolean not the string `"false"`), `0`, `""`, `''`, `undefined`, `null`, and `NaN` are falsy values.


[This]: https://stackoverflow.com/questions/4467538/what-does-the-operator-do-in-ruby