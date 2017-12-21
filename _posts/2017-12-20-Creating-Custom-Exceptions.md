---
layout: post
title:  "Creating Custom Exceptions"
date:   2017-12-20 19:36:36 -0700
categories: Ruby, StandardError, Exceptions, Error Handling
---

While working on my Tic-Tac-Toe game, I wanted to make sure that the move the player provides is valid: meaning that number provided corresponds to one of the labeled spaces on the TTT board and thus not out of range. Since Ruby does not have a `VoidMoveError` readily available for my TTT board (c'mon Ruby), I can create a custom `VoidMoveError` class.

This custom `VoidMoveError` class should inherit from `StandarError` and not `Exception` If a custom exception were to inherit from `Exception`, it would rescue every single exception that inherits from `Exception`. No exception :laughing:

That means our custom exception class would rescue some internal one's used by Ruby such as `SignalException::Interrupt` (you won't be able to exit using control c) and `ScriptError::SyntaxError` (syntax errors will fail without a peep). Here is a list of all the errors that inherit from `Exception`

~~~~
Exception
 NoMemoryError
 ScriptError
   LoadError
   NotImplementedError
   SyntaxError
 SignalException
   Interrupt
 StandardError
   ArgumentError
   IOError
     EOFError
   IndexError
   LocalJumpError
   NameError
     NoMethodError
   RangeError
     FloatDomainError
   RegexpError
   RuntimeError
   SecurityError
   SystemCallError
   SystemStackError
   ThreadError
   TypeError
   ZeroDivisionError
 SystemExit
~~~~

Since we're not interested in rescuing these types of exceptions and instead only want to catch our app specific errors, we should instead inherit from `StandardError`

`StandardError` includes errors such as `TypeError` and `NoMethodError` which are the types of errors our app's code may produce.

Let's create `VoidMoveError` and have it inherit from `StandardError`

{% highlight ruby %}
class VoidMoveError < StandardError
end

raise VoidMoveError
{% endhighlight %}

Pretty easy, right? Next let's add a message attribute so that when the error is raised, we get a little more detail about what the error means.

{% highlight ruby %}
class VoidMoveError < StandardError
  def initialize(msg="Your move is out of range. Please try again.")
    super
  end
end

raise VoidMoveError
{% endhighlight %}

This time around, we added a default message by adding our own constructor. When we raise `VoidMoveError` (without passing in a error message) the default message is passed:

`VoidMoveError: Your move is out of range. Please try again.`

