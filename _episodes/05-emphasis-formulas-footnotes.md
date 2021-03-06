---
title: "R Markdown Syntax: Emphasis, Formulas & Footnotes"
teaching: 10
exercises: 10
questions:
- How do I emphasize text in an R Markdown document?
- How do I add LaTex formulas?
- How can I make superscript text?
- How can we add footnotes?

objectives:
- Learn how to apply emphases to words or phrases in R Markdown
- Understand the power of LaTeX (Lay-techhh) for mathematics formatting
- Learn how to add equations and formulas in R Markdown 
- Learn how to add footnotes in R Markdown

keypoints:
- You can add _*italicized*_ and _*bolded*_ texts in R Markdown
- There is an extensive LaTeX guideline for mathematics formatting
- You can add create superscript text & linked footnotes 
source: Rmd
---




## Adding Emphasis

Another way we can customize our R Markdown file output is by emphasizing words or phrases. In our paper, there are several instances of words and phrases that are italicized or bolded. We use markdown syntax to add these emphasis to words or phrases by surrounding them with matching symbols. Different symbols give different emphases effects. 

Put text in italics with single asterisks or single underscores.  

```*italics*``` will give output *italics*  
```_italics_``` will give output _italics_

Make text bold with double asterisks or double underscores.  

```**bold**``` will give output **bold**  
```__bold__``` will give output _bold_  

Let's try that italics applying that to two organization names that appear in the text. First let's put the `Association of Biomolecular Resource Facilities` in italic. `_Association of Biomolecular Resource Facilities_` or `*Association of Biomolecular Resource Facilities*` will render _Association of Biomolecular Resource Facilities_. Now try the same with the `Committee on Core Rigor and Reproducibility`. 

> ## CHALLENGE 5.1 - Applying Bold Emphasis
> For testing out making the text bold, let's search for the mention to the Transparency and Openness Promotion in the paper and make them bold.
>> ## SOLUTION
>> Either `__Transparency and Openness Promotion__` or `**Transparency and Openness Promotion**` will render **Transparency and Openness Promotion**
> {: .solution}
{: .challenge}

Which symbol do you prefer to use? Do you prefer to stick with the same for both emphases? 

> ## Time to Knit!
> Check how the emphases you have just applied looks like in your paper. 
{: .checklist}

>## Tip: ***When you realllllly want to emphasize something***
> 
> you can combine emphasis styles by combining the symbols surrounding the word or phrase. 
> Make text bold and  italicized with triple asterisks or triple underscores.  
> ```***super emphasized***``` will give output ***super emphasized*** 
> ```___super emphasized___``` will give output ___super emphasized___
{: .callout}

### Adding Blockquotes

R Markdown also allows you to emphasize a pull quote using blockquotes. Let's say you want to transform the first sentence in the paper into one and also apply italic emphasis. For this you will have to add a carrot ">" (greater-than symbol) and the asterisc or underscore for the italics, as demonstrated below:.

`>_"I have seen further it is because I have stood on the shoulders of giants"_ (Isaac Newton)`

The output you will get shoul look like that:

>_"I have seen further it is because I have stood on the shoulders of giants"_ (Isaac Newton)


> ## Time to Knit!
> Check for the block quote in your paper. 
{: .checklist}


## Adding Equations & Formulas

LaTeX (pronounced Lay-techhh) is a comprehensive document formatting and preparation system.  It is very powerful, but also famously difficult to use.  A few journals require that papers be written in LaTeX, and some fields, such as high energy physics, use it exclusively.  Why?  Because, despite its difficulty, its mathematics formatting (its formatting of equations and formulas) is better than anything else out there.

RStudio has a most wonderful feature that allows you to use just the mathematics formatting portion of LaTeX without having to use LaTeX as a whole, without having a LaTeX installation on your system, and without having to understand LaTeX generally.

An inline formula is delimited with single dollar signs, as in `$ 2+2 = 4 $`.  A display equation uses double dollar signs, `$$ 2+2 = 4 $$`.  What goes between the single or double dollar signs is LaTeX math formatting.  This is its own language, and you just have to learn it.  A decent online reference (Overleaf is an online LaTeX editor):

- [https://www.overleaf.com/learn/latex/Mathematical_expressions](https://www.overleaf.com/learn/latex/Mathematical_expressions)

The canonical LaTeX reference, written by the author (hardback, but viewable online):

- [https://archive.org/details/latex00lesl](https://archive.org/details/latex00lesl)
- [https://ucsb-primo.hosted.exlibrisgroup.com/permalink/f/1egv95m/01UCSB_ALMA21230090630003776](https://ucsb-primo.hosted.exlibrisgroup.com/permalink/f/1egv95m/01UCSB_ALMA21230090630003776)

But, know that the LaTeX math language is very intuitive once you get a feel for its style.  Put your math head on, not your programming head.  If you want to say that a equals b times c, in a programming language you might write something like `a = b*c`, but in LaTeX you would say `$ a = bc $`. Spaces generally don’t matter in LaTeX; it "understands" your formula and uses rules to determine how to display things.

> ## Challenge 5.2 - Adding Formulas  
>
> Let’s add the following text and formula to our data analysis section where the paper talks about confidence level:
>
> Using the sampling error formula
>
> ```$$e = { Zp(1-p) \over \sqrt{n} }$$```
> 
> we compute that at a 95% confidence level (i.e., Z=1.96), with base probability p=1/2 and sample 
> size n=243, the margin of error is +/-3%.
{: .challenge}

> ## Time to Knit!
> Check how the formula just rendered in your paper. 
{: .checklist}

Double click on the equation. Notice how RStudio gives you a preview of it. Nice! The formula here uses curly braces for grouping (kind of like invisible parentheses). `\over` gives a fraction with a big horizontal line. Try replacing that with just `/` for an alternative rendering.

> ## Challenge 5.3 - Inline Formulas  
>
> For inline formulas, in the same section of text replace `Z=1.96` with `$Z=1.96$` and similarly. Notice the different formatting, and notice again RStudio’s preview when you hover over the formula.  In LaTeX, you would say `$ \pm 3 \% $` for the +/-3%.  Later we’ll see how to have R compute this value inline.
{: .challenge}

> ## Time to Knit!
> Check how the new formulas just rendered in your paper. 
{: .checklist}

To appreciate the beauty of LaTeX's typesetting, just look at how formulas are typeset by other systems. Here's an example: [https://www.educba.com/confidence-interval-formula/](https://www.educba.com/confidence-interval-formula/)

RStudio's facility to bring in LaTeX for math formatting makes it a wonderful authoring environment for math-rich papers that are not computational and have nothing to do with R at all.

## Adding Footnotes

We can add footnotes to our paper using the `^`. Similar to adding emphasis, putting carrot symbols around your text will print the output as a superscript. 

`^superscript^` will give output: <sup>superscript<sup>

`footnote^1^` will give output: footnote<sup>1<sup>

In our paper, we will create a footnote in the introduction when we reference a notice from the U.S. National Institutes of Health (NIH). We will add a footnote after the word “notice” by adding `^1^` right after the word. 

`notice^1^`

> ## Challenge 5.4: Creating Footnotes 
>
> Let's add a footnote to our paper. Right before the References section, add a superscript to distinguish the footnote and match it with the inline footnote. The text to the footnote will be:
>Through these four elements, the NIH intends to "enhance the reproducibility of research findings through increased scientific rigor and transparency" https://ori.hhs.gov/images/ddblock/ORI%20Data%20Graphs%202006-2015.pdf`
>
>> ## Solution
> ``^1^Through these four elements, the NIH intends to...``
>> {: .output}
> {: .solution}
{: .challenge}


> ## Time to Knit!
> Take a look at the footnote you have just created.
{: .checklist}
