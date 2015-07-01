---
layout: post
title: "Markdown Cheat Sheet"
date: 2015-06-29 16:16:42 -0400
comments: true
categories: ["Flatiron School", "markdown", "cheat sheet", "reference"]
---
Markdown is used *a lot*, so I figured a cheat sheet could be useful, so here goes: 

### [Headings](#headings)
### [Paragraphs](#paragraphs)
### [Horizontal Rule](#horizontal-rule)
### [Text Styling](#text-styling)
### [Links](#links)
### [Named Anchors](#named-anchors)
### [Images](#images)
### [Lists](#lists)
### [Quotes](#quotes)
### [Tables](#tables)


<a id="headings"></a>

##Headings 
Headings in Markdown are preceded by the octothorpe (`#`).  You can also add trailing octothorpes, but this is optional. 

``` ruby
#This is heading 1!
##This is heading 2!##
###This is heading 3!
####This is heading 4!
#####This is heading 5!
######This is heading 6!######
```

Another way to create heading 1 and heading 2 are with equal signs (`=`) or dashes (`-`) under the text you want in the header. 

``` mxml 
I'm header 1
============

I'm header 2 
------------
```


<a id="paragraphs"></a>


##Paragraphs 
Paragraphs are determined based off a new line or at least two spaces at the end of a line. 

``` mxml 
This is the first paragraph, since there is no line separating it from the next sentences.  I'm still in paragraph one.
I'm also in paragraph 1, since there's no blank line. 

I'm in paragraph 2!
```

<a id="horizontal-rule"> </a>

##Horizontal Rule
You can break up paragraphs with a horizontal line. 
***
Just do any of the following:

`___` Three underscores

`---` Three dashes

`***` Three asterisks


<a id="text-styling"></a>

##Text Styling 
For text styling, the asterisk (`*`) or underscore(`_`) is used.  
###Bold 
To make an item **bold**, use two asterisks on each side of the item. 
``` mxml
**I'm bold. :D** 
__So am I!__
I'm not. :( 
```
###Italic 
To make an item *italic*, use one asterisk on either side of the item. 
``` mxml
*I'm italic. :D*
_So am I!_
I'm not. :(
```
###Strikethrough 
To ~~strikethrough~~ an item, use two tildes (`~`) on either side of the item.
``` mxml
~~I've been struck!~~
I have not.
```

###Escaping Characters
Some characters have meaning in Markdown, so when you want them to be displayed you may run into issues.  You can escape these characters, so that you can display them without side-effects.  To do so, put a backslash (`\`) before the character. 

```mxml
2 \+ 2
\#lol  
```
The following characters have this property: 

| Symbol | Name | 
| :-: | :-----------: | 
| \# | Octothorpe |
| \+ | Plus Sign |
| \- | Hyphen |
| \\ | Backslash |
| \` | Backtick  |
| \* | Asterisk  |
| \_ | Underscore |
| \{\} | Curly Braces | 
| \[\] | Square Brackets |
| \(\) | Parentheses |
| \. | Period |
| \! | Excalamtion Point |

<a id="links"></a>

##Links 
For [links](http://www.tibsar.github.io/blog/2015/06/29/markdown-cheat-sheet/ "Markdown Cheat Sheet"), the text you want displayed is kept in brackets(`[]`), with the link kept in parentheses (`()`).  You can also include a title after the link, which generally appears as a tooltip.  These links will open in the current tab, so if you want the link to open in a new window or tab, use the html syntax. 
```
[I will be shown](http://www.thisistheurl.com/ "A Link")
[Google](http://www.google.com)
```
You can also use a reference style for links. 
``` mxml 
[Google][id]

[id]: http://www.google.com/ "Google"

```

<a id="named-anchors"></a>

##Named Anchors 
If you want to create navigation from within the page, you can use named anchors, which is basically a link. At any headings that you want to be able to jump to, add `<a id="named-anchors"></a>` so that the headings will look something like this: 

``` mxml
<a id="headings"></a>

## Headings


<a id="paragraphs"></a>

## Paragraphs


<a id="named-anchors"></a>

##Named Anchors 
```
You can also put the link of the line of the header, but this will bring you to the content and cut off the header. To create a link to each one of the headings you would do so in the same style as a normal link. 

``` mxml
[Headings](#headings)

[Paragraphs](#paragaphs)

[Named Anchors](#named-anchors)
```

[Headings](#headings)

[Paragraphs](#paragraphs)

[Named Anchors](#named-anchors)


<a id="images"></a>

##Images
Images are also similar to links.  They use the same syntax, but have an exclamation point (`!`) preceding them.  The text in the brackets will act as the alternative text, should the image not be able to load.  The text after the url is what will show up as a tooltip when the user hovers over the picture.  


``` mxml 
![Pink](https://c1.staticflickr.com/5/4149/5018040485_28c0c3d9ef_b.jpg "Pink")
```
![Pink](https://c1.staticflickr.com/5/4149/5018040485_28c0c3d9ef_b.jpg "Pink")<cite><a href="https://www.flickr.com/photos/30950973@N03/5018040485" target="_blank">Small cell carcinoma - Yale Rosen</a></cite>

You can also use a reference syntax. 

``` mxml
![Pink Two][id]

[id]: https://c2.staticflickr.com/2/1268/4698397342_64065cf293_b.jpg "Pink Two"
```
![Pink Two][id]<cite><a href="https://www.flickr.com/photos/pulmonary_pathology/4698397342/in/photostream/" target="_blank">Hypersensitivity pneumonitis Case 127 - Yale Rosen</a></cite>

[id]: https://c2.staticflickr.com/2/1268/4698397342_64065cf293_b.jpg "Pink Two"


<a id="lists"></a>

##Lists 
###Unordered Lists
To create an unordered list use either an asterisk (`*`), a plus sign (`+`), or a hyphen (`-`) followed by a space before each bullet. 

``` mxml
* This is a bullet
- This is also a bullet
  * This is a lower level 
    + Even lower 
      - And lower
        * So low 
          - Almost through the earth
+ And back up
```
* This is a bullet
- This is also a bullet
  * This is a lower level 
    + Even lower 
      - And lower
        * So low 
          - Almost through the earth 
+ And back up

###Ordered Lists
Ordered lists are pretty self explanatory.  Simply precede each item in the list with the number or letter, followed by a period, followed by a space. 

``` mxml 
1. This is the first item!
2. And this is the second 
3. I think you get it. . . 
```
1. This is the first item!
2. And this is the second 
3. I think you get it. . . 

The numbering you put doesn't necessarily affect the numbering. For instance: 
``` mxml
1. I'm number 1 
2. I'm number 2
A. I'm letter A 
64. I'm number 64
```
Produces the following list: 

1. I'm number 1 
2. I'm number 2
A. I'm letter A 
64. I'm number 64


<a id="quotes"></a>

##Quotes 
Quotes can be inserted by putting a greater than sign `>` at the beginning of the line.  To site the sourse, use the `<cite>` tags.  

``` mxml 
> My greatest pain in life is that I will never be able to see myself perform live.
><cite>Kanye West</cite>
```
> My greatest pain in life is that I will never be able to see myself perform live.
><cite>Kanye West</cite>


<a id="code-snippets"></a>

##Code Snippets 
###Inline
To create an inline code snippet (`like this!`), use the backtick (`` ` ``) on either side of the item. 

``` 
`like this!`
```
###Indented
You can create a code snippet through the use of indentation.  Add four spaces to the beginning of a line of code for this to work. 

``` mxml 
        This is code.
        Am I right?
```
    This is code.
    Am I right?

###Block 
To create block code, which is what I've been using for all of the code examples in this cheat sheet. To do this use three backticks on the top and bottom of the code snippet.  Next to the top three backticks, you can specify the language that you are writing the code in so that the syntax will be higlighted appropriately.  If you're not sure what code to use for a particular language, check out the short codes on this <a href="http://pygments.org/docs/lexers/#" target=_blank>reference guide</a>.  
``` rb
 ``` rb
 def this_is_a_method(argument)
   result = argument * (1000)
 end 
 ```
```

``` rb
def this_is_a_method(argument)
  result = argument * (1000)
end 
```


<a id="tables"></a>

##Tables 
Tables can be created through the use of pipes (`|`) to separate columns and dashes (`-`) to separate the titles from the rows. 
``` mxml
| Id | Name | Description | 
| -- | ---- | ----------- | 
| 1 | Elle Woods | Lawyer in pink |
| 2 | Emmett Forrest | Handsome husband |
| 3 | Bruiser Woods | Chic chihuahua|
```

| Id | Name | Description | 
| ------ | ----------- | ----------- | 
| 1 | Elle Woods | Lawyer in pink |
| 2 | Emmett Forrest | Handsome husband |
| 3 | Bruiser Woods | Chic chihuahua|

By default, the table will be left aligned.  If you want to center the items in the table, use colons (`:`) as follows: 

``` mxml
| Id | Name | Description | 
| :-:| :---:| :----------:| 
| 1 | Elle Woods | Lawyer in pink |
| 2 | Emmett Forrest | Handsome husband |
| 3 | Bruiser Woods | Chic chihuahua|
```

| Id | Name | Description | 
| :------: | :-----------: | :-----------: | 
| 1 | Elle Woods | Lawyer in pink |
| 2 | Emmett Forrest | Handsome husband |
| 3 | Bruiser Woods | Chic chihuahua|

You can also right align the information. 
``` mxml
| Id | Name | Description | 
| --:| ----:| ----------: | 
| 1 | Elle Woods | Lawyer in pink |
| 2 | Emmett Forrest | Handsome husband |
| 3 | Bruiser Woods | Chic chihuahua|
```

| Id | Name | Description | 
| ------: | -----------: | -----------: | 
| 1 | Elle Woods | Lawyer in pink |
| 2 | Emmett Forrest | Handsome husband |
| 3 | Bruiser Woods | Chic chihuahua|

