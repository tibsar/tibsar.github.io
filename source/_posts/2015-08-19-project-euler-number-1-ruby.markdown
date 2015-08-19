---
layout: post
title: "Project Euler #1 - Ruby"
date: 2015-08-19 07:11:32 -0400
comments: true
categories: ["Project Euler", "Ruby", "Interview Prep", "Problem Solving", "Project Euler - Ruby"]
---
I am going to start solving all of the Project Euler problems on my blog.  This will take an incredibly long time, but I believe that it's a great warm up for coding. So that being said, there's no better place to begin than with number 1. 

##Project Euler #1
> If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6, and 9.  The sum of these multiples is 23.  
> Find the sum of all the multiples of 3 or 5 below 1000. <cite>Project Euler #1</cite>

After reading the problem, I have a basic understanding of what I need to do.  I need to first find all of the multiples or either 3 or 5 that are less than 1000.  Once I have those multiples, I need to add them all together to get my solution.

###Collecting the Multiples
First I need to find all of the multiples under 1000.  In order to do that I have to know what makes a number a multiple or 3 or 5. A great way to tell is if the number in question divided by either 3 or 5 results in a whole number with no remainder.  If this is true, the number is evenly divisible by either 3 or 5 and a multiple. I know that Ruby has a great function for checking for remainders called modulo. 

``` ruby
(number_in_question % 3 == 0) || (number_in_question % 5 == 0)
```
This code will return `true` if the `number_in_question` is a multiple of 3 or 5.  However, we stil have no way of finding the `number_in_question`.

The problem gives us a hint at where to start for this part.  The problem is asking for all multiples that are below 1000.  Therefore, we need to check all numbers below 1000. That suggests that we need to use an exclusive range.  So to collect all of the numbers below 1000 in an array we can do the following: 

```ruby 
limit = 1000
(1...limit).to_a
```
However, this will collect all of the numbers below 1000, and we only want the numbers that are multiples of 3 or 5.  To do this, we can use the select method. 

``` ruby 
(1...limit).select{ |i| (i % 5 == 0 || i % 3 == 0)}
```

This will only select numbers that are less than 1000 but a multiple of either 3 or 5 and store them in an array.  Let's turn it into a function, so that it is easily accessible for our next step.

``` ruby 
def collect_multiples(limit)
  (1...limit).select{ |i| (i % 5 == 0 || i % 3 == 0)}
end 
```

###Adding the Multiples Together
Now that we have access to an array of all the multiples we want, all we have to do is add them together. Luckily, Ruby has a great function to help us out. The `reduce` function will allow us to perform an operation on all of the items in an array. So to find the sum of the multiples this is all we have to do: 

``` ruby
collect_multiples(1000).reduce(:+)
```

###Arriving at a Solution
We've done all the coding necessary to find the solution!  Now I don't want to give it away, so I'm not going to post it here, but if you're unsure if your code works or not, look at the example in the problem. Use 10 as your limit and try to get 23 as a result.  When you think you have a solution, you can sign up for a Project Euler account and submit it <a href="https://projecteuler.net/problem=1" target="_blank">here</a>. Here's some proof that this code works: 

{% img center http://i.imgur.com/SEiCPvl.png %}
And if you want to see all the code in one place: 
```ruby 
def collect_multiples(limit)
  (1...limit).select{ |i| (i % 5 == 0 || i % 3 == 0)}
end 

puts collect_multiples(1000).reduce(:+)
```

In the terminal, running `ruby file_name_here.rb` with whatever you named the file that you are coding in, will display the soluton to the terminal screen. 

If you feel that you have a better solution, post a gist to it in the comments!