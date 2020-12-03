---
title: "Markdown Syntax: Adding Citations and Bibliography"
teaching: 5
exercises: 0
questions:
- How to include citations?
- How to create a list of references? 
- How to apply different citation styles?

objectives:
- Learn how to include citations
- Create a list of references
- Learn how to apply different citation styles 

keypoints:
- FIXME
- FIXME
source: Rmd
---



## Getting the Bibliography

Let's now move our attention to include citations and list out the references (bibliography) in our paper example. Before adding citations we need to list out all citable items and set a bibliography. In order to add a bibliography we will need to include a bibliography file in the YAML header. Bibliography formats should be specified in one of the formats supported by Pandoc on RStudio:

* MOD: _.mods_
* BibLaTeX: _.bib_
* BibTeX: _.bibtex_
* RIS: _.ris_
* EndNote: _.enl_
* EndNote XML: _.xml_
* ISI: _.wos_
* MEDLINE: _.medline_
* Copac: _.copac_
* JSON citeproc: _.json_

Please note that bibliography formats are not the same as citation styles. These are specified by a CSL (_Citation Style Language_) that we will cover later on. For now, we will stick to the bibtex format which is supported by Google Scholar, which we will use to retrieve example references. If you use a reference manager such as Zotero, Endnote, Mendeley etc. to manage your library, you can also export the .bibtex file directly, with all citable items you consider to include in the paper.

```
\*.bibtex` file consists of bibliography in plain-text format. Here is an example with two entries:

``@misc{nature\_nature\_2018,

type = {Repository},

title = {Nature {Reproducibility} survey 2017},

url = {10.6084/m9.figshare.6139937.v4},

journal = {Figshare},

author = {Nature},

year = {2018},

}

@article{springer\_reality\_2016,

title = {Reality check on reproducibility.},

volume = {533},

doi = {10.1038/533437a},

number = {7604},

journal = {Nature},

author = {Springer, Nature},

month = may,

year = {2016},

pages = {437},

}
```

Note that the first line specifies the type of citation, MISC for _miscellaneous_, and Article for _papers_, along with the main entry which will be used to link in-text citations further in the episode. The other lines include the metadata that describes different parts of the bibliography, such as the date, the author, etc.

These two references are included in the `bibliography.bibtex` file supplied to you and saved on your Desktop as recommended and that you should now open in RStudio. Now let&#39;s collect the other citations we will need to include in our paper.

We want to add other four items to our bibliography list to be then cited in the paper.

1. 1,500 scientists lift the lid on reproducibility by Baker (2016).

2. The reproducibility of biomedical research: sleepers awake! By Bustin (2014).

3. Reproducibility2020: progress and priorities. By Freedman, Venugopalan, &amp; Wisman (2017).

4. A manifesto for reproducible science. By Munafò et al. (2017).

To do so, you should follow four main steps:

1. Search for the first paper listed on Google Scholar by copying and pasting the title of the paper. Make sure to use quotations to better filter results and get the right paper.A tricky part is that if you want more completed files that will render to more accurate citations you have to check for existing versions (if any) of the same result. Google Scholar amasses them altogether into one in the link &quot;All 6 versions&quot;, listing out different repositories and websites the paper must be living in.

![Fig. 7.1 - Bibtext from Google Scholar (1)](../fig/07-gs-bibtex1.png)

Click on the link to check for other existing versions. The first result does include the journal name, so let's choose the second one instead, which won't require us to adjust the metadata.

![Fig. 7.2 - Bibtext from Google Scholar (2)](../fig/07-gs-bibtex2.png)

2. When you click on the quotation icon right below the version you chose, it will prompt a window that will give you the option to choose BibTeX.

![Fig. 7.3 - Bibtext from Google Scholar (3)](../fig/07-gs-bibtex3.png)

3. Clicking on the BibTeX option will open the file in your browser, like this:

```
@article{baker20161,

title={1,500 scientists lift the lid on reproducibility.},

author={Baker, Monya},

journal={Nature: International weekly journal of science},

volume={533},

number={7604},

pages={452--455},

year={2016},

publisher={Macmillan}

}
```

4. Copy and paste this to your bibliography.bibtex file. The order is not important. You can either copy before or after items provided. All items will be organized according to the style. It is strongly recommended to have entries separated by blank lines. That makes them look like paragraphs, and easier to locate.

> ## Challenge 7.1: Complete the .bibtex file 
>
> Get all six citable items in the file using Google Scholar
>
>
> ~~~
> Now, follow the same process with the remaining three references.
>
> 1. The reproducibility of biomedical research: sleepers awake! By Bustin (2014).
>
> 2. Reproducibility2020: progress and priorities. By Freedman, Venugopalan, &amp; Wisman (2017).
>
> 3. A manifesto for reproducible science. By Munafò et al. (2017).
>
> ~~~
> > ## Solution
> 
> 
> > ~~~
> Your bibliography.bibtex file tab should have a total of six items once you complete this task. 
> FIXME: should we add all items here?
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}


**Tip:** Alternatively, you can also conduct multiple searchers and save results to your personal library on Google Scholar and export multiple items as.bibtex files in a bulk.

We should now have a complete .bibtex file with all items we need to proceed. But how will RStudio be able to link this file with the .rmd file on the other tab? Well, remember we mentioned early on that we should include a bibliography file in the YAML header? In this case we will add to the existing YAML the following information:

```
---

bibliography: bibliography.bibtex

---

```

The connection between the two files is all set to get us started. For now, we won't need to specify which format we would like to use. By default, Pandoc will use a Chicago author-date format for citations and references and we will stick with that for now, but later we will learn how to change citation styles.

### Adding Citations

Each item in the bibliography.bibtex file starts with a @ entry which specifies the type of document followed by a curly opening bracket which specifies the key that should be included to create in-text citations.

It is important to use this exact key to render correct mentions in the text. Let&#39;s see how that should be included in the R Markdown syntax.

#### Single citation

At the end of the first paragraph on the Introduction, where you find `[citation example 1]`. Remove this info and let&#39;s practice adding our first citation. Let&#39;s use the item with the key `freedman\_2020\_2017` from the bibliography.bibtex file in the second tab. In order to cite this work you should add this key after an &quot;@&quot; in between brackets, as follows:

```
[@freedman\_2020\_2017]

The output you will get in Chicago style will be:

(Freedman, Venugopalan and Wisman 2017)

```

> ## Challenge 7.2: Adding single citation
>
>
>
> ~~~
> 
>Locate [citation exercise 1] in the document, and replace it by a citation to Mufano's study.
>
> ~~~
> > ## Solution
> 
> 
> > ~~~
> 
> `[@munafo\_manifesto\_2017]` 
> The output you will get in Chicago style will be: `(Mufano, 2017)`
>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}


#### Multiple Citations

If you want to add multiple citations in a row (same parenthesis) you will have to separate keys by semicolon. So let&#39;s complement the citation we created earlier in the first paragraph by adding Bustin&#39;s to it:

`[@bustin\_reproducibility\_2014; @freedman\_reproducibility2020\_2017]`

The output you will get in Chicago style will be:

`(Bustin, 2014; Freedman, Venugopalan and Wisman, 2017)`

*Tip:* You can simplify items key if you want. For instance, you can keep only the first author and year, but for the purpose of the exercises we will keep keys exactly how exported from Google Scholar.


> ## Challenge 7.3: Adding multiple citations
>
>
> ~~~
> 
> Now it is your turn! Locate in the document the note [citation exercise 2]. Remove it and include a citation to Baker and Freedman, Venugopalan and Wisman&#39;s studies.
>
> ~~~
> > ## Solution
> 
> 
> > ~~~
> 
> `[@baker\_1500\_2016; @freedman\_reproducibility2020\_2017]`
> The output you will get in Chicago style will be: `(Barker, 2016; Freedman, Venugopalan and Wisman, 2017)`
>
>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}


#### Keeping Authors in the narrative

There are cases authors are announced in the text, and therefore their names shouldn&#39;t go between parenthesis. Let&#39;s say you want to add a citation to support the statement about Springer&#39;s survey. In order to keep the institutional author out of the parentheses, we should add a - sign before the @ followed by the citation key, as it follows:

&quot;A recent survey conducted by_Springer_ `[-@springer\_reality\_2016]` reported that 90%...&quot;

The output you will get will be:

&quot;A recent survey conducted by Springer (2016) reported that 90%...&quot;


> ## Challenge 7.4: Keep author(s) in the narrative 
>
>
> ~~~
> 
> Let&#39;s practice now how to insert citations outside the paranthesis! In the same paragraph, where you find `[citation exercise 3]` add a citation (year only) to your mention to Nature&#39;s survey in order to indicate the dataset you are referring to.
>
> ~~~
> > ## Solution
> 
> 
> > ~~~
> 
> 
> `[-@nature\_nature\_2018]`
> The output you will get will be: `Nature (2018)`
>
>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}


### Setting the Reference List

All cited items will be listed under the section **References** which you created before while practicing headings and subheadings. Items will be placed automatically in alphabetical order.


#### Add an item to a bibliography without citing it

By default, the bibliography will only display items that are directly referenced in the document. If you want to include items in the bibliography without actually citing them in the body text, you can define a dummy nocitemetadata field and put the citations there.

```

nocite **:** |

@item1, @item2

```

#### Add all no-cited items to the bibliography

If we do not wish to explicitly state all of the items within the bibliography but would still like to show them in our references, we can use the following syntax:

```
nocite: |
  @item1, @item2

```

This will force all items to be displayed in the bibliography.

### Changing Citation Styles

There are a number of existing [citation styles](https://editor.citationstyles.org/about/) (CSL), but we won&#39;t cover their differences and applications during this workshop. To use another style, we will need to specify a CSL (Citation Style Language) file in the metadata field in the YAML header.

Let's assume that we want to use the APA 5th edition [apa-5th-edition.csl](https://github.com/citation-style-language/styles/blob/master/apa-5th-edition.csl). In order to do so, you have to make sure the CSL you want to apply is correctly named in the YAML, matching the .csl file saved in the project folder and opened in RStudio. Your YAML should look similar to this:

```
title: "An Adapted Survey on Scientific Shared Resource Rigor and Reproducibility"

author: Your Name

date: "December 15, 2020"

output:

html\_document:

number\_sections: true

bibliography: bibliography.bibtex

csl: apa-5th-edition.csl

```


Knit the document and note that citations and references now conform to the APA style.

**Tip:** You can override this default by copying a CSL style of your choice to default.csl in your user data directory.The CSL project provides further information on [finding and editing styles](https://github.com/citation-style-language/styles).More information about CSL can be found here [https://docs.citationstyles.org/en/1.0.1/primer.html](https://docs.citationstyles.org/en/1.0.1/primer.html).