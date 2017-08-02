---
layout: post
title: Terseness
---

### Exploring the Rubyist Way
>"I want to solve problems I meet in the daily life by using computers, so I need to write programs. By using Ruby, I want to concentrate the things I do, not the magical rules of the language ... So I have tried to make Ruby code concise and succinct." - Yukihiro Matsumoto (Matz)

Ruby is a coding language that allows the programmer to get the point without getting bogged down (too much) by the syntax of the language. There are so many methods built within it that when transitioning to another language, could make it seem like a chore.

Let's quickly compare one example of reversing a string in JavaScript and in Ruby.

I originally started off learning JavaScript and the most basic way I thought  to reverse a string:  

```javascript
var string = "This is a string"
string = string.split("").reverse().join("")
# => 'gnirts a si sihT'
```
Which is works, but, since you're only able to call reverse on an array, you first have to convert the string into an array and then back again into a string. However, if you were using Ruby to do the same thing and manner, you could simply:  

```ruby
string = "This is a string".reverse
# => "gnirts a si siht"
```
Now, I admit, this is a very basic example and you might rarely need to reverse a string except for a beginner coding challenge testing to explicit do so or check for a palindrome. Which...

```ruby
def palidrone_checker(word_in_question)
	word_in_question == word_in_question.reverse
end

```
That would work in most basic conditions and allow you to give yourself a nice pat on the back. Now, this post isn't to bash on another other language or put Ruby on a pedestal. Rather, a good programmer with ample knowledge of the tools at hand can get the job done. That said, let's work on some good practices that could make the task easier!

### Implicit Returns
When you write a method in Ruby, you don't have explicitly use a `return` keyword. It'll automatically know to return the last line of code that was written in the method.

~~~ruby
def hello_world
	"hello world"
end
# => "hello world"
~~~
However, that's not to say that you can't use `return`, just that by convention Rubyists tend not to use it and Ruby doesn't need you to tell it do it.

```ruby
def hello_word
	return "hello world"
end
# => "hello world"
```
Again, to reiterate, know the tools at your disposal and when to use them. If you were to explain Ruby to a beginner, you might want to include `return` in your code and eventual introduce them to the concept of implicit returns. On the other hand, if you know that your code is being read by a fellow Rubyist, they might give you an odd stare after seeing all the `return`s. `¯\_(ツ)_/¯`

### Ternary Operators
Ternary operator isn't a concept unique to Ruby. In fact a quick search on [wikipedia] (https://en.wikipedia.org/wiki/%3F:) will pull an enormous list of languages that this conditional operator.

Conditionals are usually written in the following format (again with Ruby)

~~~ruby
this_is_true = true
this_is_false = false

def if_else_comparison(condition)
	if condition
		true
	else
		false
	end
end

if_else_comparison(this_is_true)
# => true
if_else_comparison(this_is_false)
# => false
~~~

Let's see the same method written using a ternary operator:

~~~ruby
this_is_true = true
this_is_false = false

def ternary_operator_example(condition)
	condition ? true : false
end

ternary_operator_example(this_is_true)
# => true
ternary_operator_example(this_is_true)
# => false
~~~

Initially, it might not seem that intuitive, but it's actually not that hard to use. What's happening when you use a ternary operator is that the condition to the left of the `?` gets evaluated and if it's truthy, the value on the left of the `:` gets returned; if it's falsey, the value on the right gets returned.


Take a look back up and notice the difference in lines and the amount of code written. If you're going to write an if-else statement and you're evaluating a condition and returning one of two values, consider a ternary operator. You'd still have to keep in mind if the condition you're checking is extremely long or wordy, you might just want to default to the traditional if else statements. In other words, be logical about it. ( ͡~ ͜ʖ ͡°)

Last thing about ternary operators, you can nest them:

~~~ruby
def fizz_buzz_checker(num)
	num % 5 == 0 && num % 3 == 0 ? "FizzBuzz" : num % 3 == 0 ? "Fizz" : num % 5 == 0 ? "Buzz" : num
end

fizz_buzz_checker(3)
# => "Fizz"
fizz_buzz_checker(5)
# => "Buzz"
fizz_buzz_checker(15)
# => "FizzBuzz"
fizz_buzz_checker(1337)
# => 1337
~~~

... and if your head hurts and your eyes are glazed over, I don't blame you. That's NOT how ternary operators are supposed to be used. Ternary operators are a way of making your code more concise. A better alternative is the conventional `if-elsif` statements. But... if your recruiter is giving you a hard time, and you are tired of the 'safe' way, give it a try. `(͡◔ ͜ʖ ͡◔)`

### Statement Modifiers (using `if` and `unless`)
As mentioned before, Ruby is great for its functionality and readability. Sometimes, you can read the code as if it were written in English. Take a look at the following code and see how it'd work using the traditional `if-else` statements.

~~~ruby
ruby = "easy to read"

def easy_to_read?(language)
	if language == "easy to read"
		true
	end
end

easy_to_read?(ruby)
# => true
~~~

So, basically, we're checking to see if the language is "easy to read" and if it is then we'll return `true`. If it's `false` I'm not really concerned about it anyway. But, we can do that same thing, using a statement modifier:

~~~ruby
ruby = "easy to read"

def easy_to_read?(language)
	true if language == "easy to read"
end

easy_to_read?(ruby)
# => true
~~~

It only took one line! `ᕙ( ͡° ͜ʖ ͡°)ᕗ` And the same type of logic can be applied using `unless`

~~~ruby
ruby = "still easy to read"

def still_easy_to_read?(language)
	true unless language == "difficult to read"
end

still_easy_to_read?(ruby)
# => true
~~~

Just to practice using `unless` and not have it evaluate it to true.  

~~~ruby
klingon = "difficult to read"

def still_easy_to_read?(language)
	true unless language == "difficult to read"
end

still_easy_to_read?(klignon)
# => nil
~~~
`unless` is a trickier concept to grasp, but when read as used in the block of code above, it makes a bit more sense; "return this value `unless`... this condition is true".

---

In conclusion, Ruby has so many methods to help you find a solution to your problem. Knowing what's available to you is half of the problem, the other half relies on you to know when to use these tools. Hope these tips and tricks helped you think about some good practices and aid you in writing more concise code.  `( ͡° ͜ʖ ͡°)>⌐■-■` `(⌐▀͡ ̯ʖ▀)`

---

#### Resources:

	Ternary Operators
		- http://www.dnawebagency.com/ternary-operator/  
	Interview with Matz
		- http://www.artima.com/intv/rubyP.html
	Statement Modifiers
		- http://rubylearning.com/satishtalim/simple_constructs.html
	Ruby Returns
		- http://jtrudell.github.io/blog/ruby_return_values/
	Inspiration
		- http://content.time.com/time/magazine/article/0,9171,1570810,00.html
