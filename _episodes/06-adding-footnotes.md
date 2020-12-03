---
title: "Markdown Syntax: Adding Footnotes & Hyperlinks"
teaching: 5
exercises: 0
questions:
- How can we add footnotes?
- How can we add hyperlinks?

objectives:
- Learn how to insert footnotes 
- Learn how to create hyperlinks

keypoints:
- FIXME
- FIXME
source: Rmd
---

# Markdown Syntax: Adding Footnotes & Hyperlinks

## Adding footnotes

We can add footnotes to our paper using the ^ symbol. Similar to adding emphasis, putting carrot symbols around your text will print the output as a superscript. 

`superscript^1^` will give output: superscript^1^

`^1^footnote` will give output: ^1^footnote

In our paper, we have a footnote in the introduction when we reference a notice from the U.S. National Institutes of Health (NIH). We will add a footnote after the word “notice” by adding `^1^` right after the word. 

`notice^1^`

> ## Challenge 6.1: Creating footnote 
>
>Let's add a footnote to our paper
>
> ~~~
>
> In the References section, add a superscript to distinguish the footnote and match it with the inline footnote.  
> ~~~
>
> > ## Solution
> 
> > ~~~
>
> `^1^Through these four elements, the NIH intends to`
>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}


## Creating Hyperlinks

Hyperlinks are created using the syntax `[text](link)` with no spaces in between the parentheses and the square brackets.

For example:

`[RStudio](https://www.rstudio.com)`

Knit it and see what it will render:


[RStudio](https://www.rstudio.com)

Now, let’s apply it to the template paper. Find where the “Center of Open Science” is mentioned and link the institution to their official website:

`[Center for Open Science](https://www.cos.io/)` 


> ## Challenge 6.2: Adding links 
>
>Let's add links to our paper
>
> ~~~
>
> Now it is your turn! We want to create two hyperlinks. One will be to the survey instrument platform Survey Monkey (https://www.surveymonkey.com/). The second will be to link the existing address that we added earlier in the footnote to the online pdf file using the same website. 
> ~~~
>
> > ## Solution
> >
> >
> > ~~~
> >
> `[SurveyMonkey](https://surveymonkey.com)`

>`([https://ori.hhs.gov/images/ddblock/ORI%20Data%20Graphs%202006-2015.pdf_](https://ori.hhs.gov/images/ddblock/ORI%20Data%20Graphs%202006-2015.pdf))`
>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}


*Tip:* You can use html directly in your .rmd document to add a link that will open in a new tab, such as `<a href="http://www.ucsb.edu/" target="_blank"> UCSB</a>`. This syntax requires pandoc and link_attributes extension, that is by default included in Rmarkdown.