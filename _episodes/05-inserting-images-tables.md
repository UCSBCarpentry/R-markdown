---
title: "Inserting Images and Tables"
teaching: 30 min
exercises: 10 min
questions:
- How do I insert an image or table into rmarkdown?
- How do I align images or tables?

objectives:
- To insert images into an rmarkdown document 
- To add tables into an rmarkdown document

keypoints:
- FIXME
- FIXME
source: Rmd
---


##Inserting Images

You can add images to an R Markdown report using markdown syntax as follows:
![Image Name](path-to-image-here)

However, when you knit the report, R will only be able to find your image if you have placed it in the right place - RELATIVE to your .Rmd file. This is where good file management becomes extremely important. We have placed all our images in the figs  folder. In that case, make sure your path starts with figs/ along with the correct image name and file extension. Also the closing bracket and the opening parentheses should be close to each other, without any spaces in between.
In our paper template there are three images (two pie charts) and one bar chart we want to include. Those are named fig1_paper.jpg, fig2_paper.jpg and fig3_paper.jpg.

FIXME Add images here.

To start let’s identify where Figure 1 is first mentioned in the paper. We will be adding it with the following name: FIGURE 1 - Survey respondents#39; self-assessments of their knowledge and awareness of the current NIH guidelines on rigor and reproducibility (shared in the chat).
The markdown should look like:

![FIGURE .1 - Knowledge and awareness of the current NIH guidelines on rigor and reproducibility.](figs/fig1_paper.jpg)

Save it and use the knit function to check how the output looks like. 
Resizing Images 
The image you just added looks a little too big, right? We can resize it by adjusting the width and height ratio. Let’s say we want this image to be half of the original size. In order to do that, we will have to add to the syntax: 

![FIGURE 1 - Knowledge and awareness of the current NIH guidelines on rigor and reproducibility.](figs/fig1_paper.jpg){width=50% height=50%}


>## CHALLENGE 5.1
>
>Include figures 2 and 3 to the document. With the following names:
>
>FIGURE 2 - Lack of requests for rigor and reproducibility documentation by users of shared resources
>
>FIGURE 3 - Types of tools that cores would like to implement in their operations
>
>The bar chart should use a ratio of 60% x 80% in order to improve readability.
> >
> > ##Solution:
> >
> >
> > ~~~
> > ![FIGURE 2 - Lack of requests for rigor and reproducibility documentation by users of shared 
> >resources](figs/fig2_paper.jpg){width=50% height=50%}
> >
> > ![FIGURE 3 - Types of tools that cores would like to implement in their 
> > operations.](figs/fig3_paper.jpg){width=60% height=80%}
> > ~~~
> >{: .output}
> {: .solution}
{: .challenge}

Aligning Images 
Similar to text all images are aligned to the left by default in Rmarkdown. If we want images to be center aligned we use HTML syntax using the <center> tag.

<center>
![FIGURE 3 - Types of tools that cores would like to implement in their operations.](figs/fig3_paper.jpg){width=60% height=80%}
</center>


>## Tip
> But if we want to be more effective and get all images aligned in a certain way, it is best to 
  apply a more general code chunk that will be covered later on, in the Knitr syntax.
{: .callout}

##Inserting Tables
We can also use markdown syntax to insert a formatted table into our document. The basic syntax to insert a table looks like this.

Column Header | Column Header
---           | ---         .     
Cell 1        |  Cell 2     .    
Cell 3        |  Cell 4     .    

Start with the column names/headers. Separate columns with the pipe ( | ) symbol. Right below the column headers use at least three dashes to separate the headers from the cells of the table. Then fill in the contents of the table row by row, separating columns using the pipe ( | ) symbol. 

Note: the spacing between cells in each row can help with readability in the rmarkdown file, but is not necessary to get the correct output. As long as the pipe symbol is there, RMarkdown will automatically format the table in your output. The following syntax will print the same table as the spaced out table above.

Column Header | Column Header
---  | ---
Cell 1 | Cell 2
Cell 3 | Cell 4

>## Note:
> you can use text emphasis in the table using the same syntax as you use when emphasizing other 
  plain text. The following change will bold the column headers in the output. 
{: .callout}



**Column Header** | **Column Header**
---               | ---             .
Cell 1            |  Cell 2         .
Cell 3            |  Cell 4         .

Let’s create Table 1 in our paper in section 3.2 Current Landscape for Rigor and Transparency in Represented Shared Resources. 

Start with the column headers “Category” and “N” in bold. Then add the separator between the header and the cells. We’ll also type out the first two rows of the table.

**Category** | **N**
--- | ---
Poor sample quality from users/sample variability/limited biological material | 51
Lack of well-trained principle investigators and lab members/Poor oversight | 45

> ## CHALLENGE 5.2: Finish Table 1 by adding the rest of the rows.
>
> ~~~
>**Category** | **N**
--- | ---
Poor sample quality from users/sample variability/limited biological material | 51
Lack of well-trained principle investigators and lab members/Poor oversight | 45
Poor experimental design: Lack of sufficient replicates/inadequate sample size/lack of adequate controls | 43 
Inadequate standardization of protocols or guidelines, and data analysis | 43 
Cost and time | 39 
Failure to leverage the core’s expertise/following the core’s advice/no consulting beforehand | 23 
Inadequate documentation of experiments/data management | 19 
Instruments: maintenance, upgrades, changes | 15 
Responses that could not be assigned to a category | 11
> ~~~
{: .challenge}

Note: There are some packages that allow you to make more advanced and interactive tables. Here are some references for these packages.
https://cran.r-project.org/web/packages/kableExtra/vignettes/awesome_table_in_html.html
https://www.htmlwidgets.org/showcase_datatables.html