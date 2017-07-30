---
layout: post
title: Terseness
---

# Exploring the Rubyist Way
>"I want to solve problems I meet in the daily life by using computers, so I need to write programs. By using Ruby, I want to concentrate the things I do, not the magical rules of the language ... So I have tried to make Ruby code concise and succinct." - Yukihiro Matsumoto (Matz)

Ruby is a coding language that allows the programmer to get the point without getting bogged down (too much) by the syntax of the language. There are so many methods built within it that when transitioning to another language, could make it seem like a chore.

Let's quickly compare one example of reversing a string in JavaScript and in Ruby.

Now I originally started off learning JavaScript and the most basic way of reversing a string:  

```JavaScript
JavaScript Example
var string = "This is a string"
string = string.split("").reverse().join("")
# => 'gnirts a si sihT'
```
Which is works, but, since you're only able to call reverse on an array, you first have to convert the string into an array and then back again into a string. However, if you were using Ruby to do the same thing and manner, you could simply:  

```ruby
Ruby Example
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

##Implicit Returns
When you write a method in Ruby, you don't have explicitly use a `return` keyword. It'll automatically know to return the last line of code that was written in the method.

~~~ruby
def hello_world
	"hello world"
end
# => "hello world"
~~~
However, that's not to say that you can't use `return`, just that by convention Rubyists tend not to use it and Ruby doesn't need you to tell it do it.

```
def hello_word
	return "hello world"
end
# => "hello world"
```
Again, to reiterate, know the tools at your disposal and when to use them. If you were to explain Ruby to a beginner, you might want to include `return` in your code and eventual introduce them to the concept of implicit returns. On the other hand, if you know that your code is being read by a fellow Rubyist, they might give you an odd stare after seeing all the `return`s. ¯\\\_(ツ)_/¯

##Ternary Operators
Ternary operator isn't a concept unique to Ruby. In fact a quick search on [wikipedia] (https://en.wikipedia.org/wiki/%3F:) will pull an enormous list of languages that this conditional operator.

Conditionals are usually written in the following format (again with Ruby)
~~~Ruby
def you
~~~


http://www.dnawebagency.com/ternary-operator/
http://www.artima.com/intv/rubyP.html
