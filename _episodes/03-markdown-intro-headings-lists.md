---
title: "Markdown Syntax: Creating Headings & Lists"
teaching: 30 min
exercises: 10 min
questions:
- How to find your way around RStudio?
- How to start an R Markdown document in Rstudio?
- How is an R markdown document configured?

objectives:
- Key Functions on Rstudio 
- Learn how to start an R markdown document 
- Understand the anatomy of an R Markdown file

keypoints:
- FIXME
- FIXME
source: Rmd
---

## Intro to R Markdown Syntax

Before we dive into learning R Markdown Syntax, let's talk a little about the "markdown" part.

R Markdown is a format for writing reproducible, dynamic reports with R which allows you to weave together narrative and code to produce elegantly formatted outputs. In practice, it allows you to use plain text for a document with bits of other things thrown in, but which will ultimately be converted to any number of other languages, for eventual display in the format you desire. It supports dozens of static and dynamic output formats such as HTML, PDF, MS Word. 

The text in an R Markdown document is written with the markdown syntax, which is a basic markup language that conveys how text should be displayed. The basic markdown syntax has dozens of flavors, of which R Markdown is one. Most markdown syntax is preserved and works identically no matter what flavor you use. However, the different flavors will have different options or slightly different implementations of certain things. 

R Markdown syntax is relatively simple and there are a number of tutorials and cheat sheets available online that you can consult while working on your reproducible report. In the next episodes we will be covering a subset of it, focusing on the most common formatting you may need to apply while writing reproducible documents. 

## Creating Headings and Subheadings

Most papers or articles need headings and subheadings to distinguish different parts of the paper. We can insert headings and subheadings in R Markdown using the pound sign (#). There are six heading/subheading sizes in R Markdown. The number of pound signs before your line of text determines the heading size, 1 being the largest heading and 6 being the smallest. 

\ # Heading 1  
\ ## Heading 2  
\ ### Heading 3  
\ #### Heading 4  
\ ##### Heading 5  
\ ###### Heading 6  

Output:  
# Heading 1  
## Heading 2  
### Heading 3  
#### Heading 4  
##### Heading 5  
###### Heading 6  

> Tip: Headings
> Note: Be sure to put a space between the last # and the start of your heading text so R Markdown > recognizes where your heading text starts. 
{: .callout}


We want to insert headings and subheadings to divide our paper into more readable parts. Let’s start by adding one at the beginning to start our introduction. In the first line of our paper, make the word “introduction” into a large heading by adding a “# “ before the line. 

# INTRODUCTION

Now we can go to the next section and add a main heading and a subheading. Find the “Materials and Methods” section (right after the introduction) and make the line that says “Materials and Methods” into a large heading and the lines that say “Survey Overview” and “Data Analysis” into subheadings. 

\ # MATERIALS AND METHODS
\ ## Survey Overview

\ ## Data Analysis


If you wish to create divisions between sections, you can insert a horizontal line in using 3 (or more) dashes or asterix:


> \ ---
>
> Some paragraph text between horizontal lines
>
> \ ***
>
> Output:
> ---
> Some paragraph text between horizontal lines
> 
> ***
> {: .source}


CHALLENGE 3.1

Insert headings throughout the rest of the paper so it is split into 5 sections (Introduction, Materials and Methods, Results and Discussion, Conclusion, and References). Use the search function in R Markdown to find these lines in the document. 

# INTRODUCTION

# MATERIALS AND METHODS

# RESULTS AND DISCUSSION

# CONCLUSION

# REFERENCES

CHALLENGE 3.2

Insert subheadings to divide our main sections into subsections. Since we already put the subheadings into the Materials and Methods section, we just need to do the Results and Discussion Section. Find the lines with.
Survey Demographics
Current Landscape for Rigor and Transparency in Represented Shared Resources
Core Implementation of Research Best Practices
Strategies for Improving R&R in Core Operation

## Survey Demographics

## Current Landscape for Rigor and Transparency in Represented Shared Resources

## Core Implementation of Research Best Practices

## Strategies for Improving R&amp;R in Core Operation

3 pt. 3 Creating Bulleted and Numbered Lists

Academic articles often include lists to make important findings stand out more or to summarize key points for readers. We will learn how to create both unordered lists with bullet points, and ordered numbered lists. 
Unordered Bullet Lists

Creating unordered lists is relatively simple. For unordered lists, you can use: asterix, dash or plus characters  *, - or +:  
* A bullet point
- Also a bullet point
+ Still a bullet point  
Output:
A bullet point
Also a bullet point
Still a bullet point

CHALLENGE 3.3
Now let’s practice creating bullet lists. Use the search function in RStudio to locate the phrase “At least 170”, in the example academic paper. This sentence and the following two should be turned into bullet points. 
Answer:
* At least 170 (∼80%) respondents use documentation, in the form of quality control and standard operation procedures (SOPs) to support practices. 
* The incorporation of an instrumentation management plan, was not as highly utilized (56%).
* Oversight of data analyses and double-checking results were some of the least widely used ones (26%).
Remember: You can use + or - too.
You can also add sub-levels, to create sub-lists by indenting the next list item evenly by two or four spaces:
* A bullet point
  * Sub-level one
    * Sub-level two 


Output:
A bullet-point
Sub-level one
Sub-level two
Ordered Numbered Lists
For ordered lists, you use a number with a dot, e.g: 1.  Your numbers do not need to be sequential.  Markdown will number the item in the order in which they appear rather than their numeric order.
1. First item in our numbered list
7. Second item in our numbered list
2. Third item in our numbered list

First item in our numbered list
Second item in our numbered list
Third item in our numbered list
Note: Markdown parser does not accept parenthesis as a list delimiter, so if you use parenthesis, the output will be the same as above.

CHALLENGE 3.4
Use RStudio to locate the paragraph which ends with “in grant applications, as follows:” the next four sentences should be shown as numbered a list.
Answer:
1. scientific premise forming the basis of the proposed research 
2. rigorous experimental design for robust and unbiased results
3. consideration of sex and other relevant biologic variables
4. authentication of key biologic and chemical resources

If needed, you can also combine sub-levels numbers or even combine bullets and numbered items in the same list, by indenting different levels. 