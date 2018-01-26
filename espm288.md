ESPM 388
================
Sara Kahanamoku
1/18/2018

Introduction
------------

See <https://espm-288.carlboettiger.info/intro> for further details.

Simulations: build future models from present models (can we incorporate past information? Priors?) How to best integrate simulated or high-resolution modern data (e.g. satellite data) with heterogenous fossil data?

"Big data" is big enough to be a problem (not an absolute number; rather, it is a bottleneck). Scientific "big data" looks very different from that of traditional tech industries. Rather than having to solve problems about the speed and quality of data transfers, scientists must grapple with bottlenecks in data aquisition, quality assurance, metadata access, data deposition, and data analysis. While scientists are relatively well-versed in churning through the process of data aquisition and analysis, we are not as good at making our workflows **reproducible**.

Different ways for data to be bid: \* Volume: the traditional problem \* Variety: abundance of formats makes wrangling data difficult \* Velocity: data changes too fast for computer to keep up

### What is data science?

Data science is a cultural term, one that is considered to define an area of study that represents the intersection of: 1. Hacking skills 2. Math and statistics knowledge 3. Substantive expertise Data science is the **intersection of all three.** If you are not a scientist, working on scientific problems, you are not a data scientist. Data science is *guided by questions*: questions come first; all methodology is in service of your specific question.

Data science, however, involves much more than just broad classes of skills. Rather, data scientists must employ a wide variety of techniques, which themselves deserve more formal treatment by the scientific community. These include: 1. Data exploration and preparation 2. Data representation and transformation 3. Computing with data 4. Data modeling 5. Data visualization and presentation 6. Science **about** data science (See Donoho's "50 years of data science" for a more thorough treatment of the field and caveats of Data Science.)

### Data science as a process

Wickham's `tidyverse` depiction is a modern take on data science: he sees data science as a process, not a static treatment. It involves importation of data, data cleaning and wrangling (tidying and transforming), data visualization, modeling, and, finally, communication. In fact, we now spend the majority of our time cleaning and preparing data, whereas, in the past, analyses and models took up the bulk of any scientist's workday. In the modern area, software has made statistics fairly fast and simple, while it still struggles with the sheer size and variety of the data that scientists can now produce.

Today, data visualization and analysis has become a bottleneck. Because data visualization is time-consuming, it is often the last step taken. Bad scientists! Visualization should rather be a primary focus: visualizing data often provides direction for EDA, and can make startling trends more apparent earlier.

Types of data repositories: \* vertically integrated: give us the common denominator; we will through out pieces of data that don't fit (e.g., PBDB!). \* unstructured data. "data lake": toss all of the data "natively" into the lake, then perform a "schema on read": clean the data when you read it in; extract data on demand.

Given that most of the data we collect are yet to come, we want to build a pipeline that is *reproducible* so that we can then come back and perform similar analyses in the future, with more data. (See **The Economist**'s "How science goes wrong" on the importance of reproducibility.)

But reproducibility isn't just about "morality": rather, science is more impactful is researchers can *build on* the work that others have done in the past. See Peng (2011) <doi:10.1126/science.1213847>.

We must focus on presenation above all things! Make sure that the code that you produce is understandable.

*Write code for people. Write data for computers.* (Buffalo 2015)

R is a good language for communicating with people! The best way to write code for people is to **not write a lot of code.** (Bless you, Carl.)

### Logistics

<https://espm-288.carlboettiger.info/policies/>

**git** <http://stevelosh.com/blog/2013/04/git-koans/>

**Advanced R textbook** <http://adv-r.had.co.nz/>

25 January 2018: Workflow: GitHub, RMarkdown, Travis
----------------------------------------------------

-   See links to *R for Data Science* by Hadley and Garrett for further elaboration on RMarkdown (and RStudio's rmd cheat sheet)

-   Happy Git with R: <http://happygitwithr.com/>

-   Datacamp: accept invitation from Carl?

RMarkdown
---------

What are the basics of RMarkdown?

-   Learned that you can insert code chunks with `Cmd-Alt-I`.

-   `Cmd-Shift-1`: fullscreen RMarkdown

-   RNotebook and RMarkdown are the same thing (woo rebranding!) but RMarkdown has slightly more options.

-   Github documents are the primary RMarkdown files we will work with during the course

Knuth's concept of **literate programming**: can we generate documentation *where we write code*? (see Roxygen documentation later...). This approach put the focus on documentation *first*, and embedded code as a secondary product. (Knuth invented "weave", which was adopted by R when it was still S, which is why it's called "sweave"...!)

Markdown was initially used to wrtie HTML, but has now become a way to write *anything* by translating that markup into different languages. Pandoc is used to translate markdown documents written in a number of languages. (Pandoc was written by a philosophy professor who is still at Berkeley!)

Markdown --&gt; intermediate markdown file (md) --&gt; Pandoc --&gt; file of desired format

(Jupyter also uses pandoc!)

GitHub
------

Travis
------