---
layout: post
title: "How to Turn an Array Into a Hash Using Ruby"
date: 2015-07-17 15:35:49 -0400
comments: true
categories: ["Flatiron School", "Refactor Tips", "Tutorial", "Arrays", "Hashes", "Ruby"]
---
It seems like the hardest part of learning a language is knowing its tricks.  In Ruby, one of these tricks is turning an array into a hash.  So let's get started!


Suppose you have the following array: 

``` ruby 
elegance_level = ["wedding", 10, "yacht", 10, "shack", 0, "wine", 8, "beer", 3, "cologne", 6]
```

This array seems to be assigning a level of elegance to the item before it, so a hash may be better suited for it.  You could iterate through the array and assign the values into a hash, however Ruby provides an easier way to accomplish this: 

``` ruby 
Hash[*elegance_level]
 => {"wedding"=>10, "yacht"=>10, "shack"=>0, "wine"=>8, "beer"=>3, "cologne"=>6} 
```

That's it! Hope you enjoyed this short but sweet refactor tip!
