ESPM 388
================
Sara Kahanamoku

## Introduction

See <https://espm-288.carlboettiger.info/intro> for further details.

Simulations: build future models from present models (can we incorporate
past information? Priors?) How to best integrate simulated or
high-resolution modern data (e.g. satellite data) with heterogenous
fossil data?

“Big data” is big enough to be a problem (not an absolute number;
rather, it is a bottleneck). Scientific “big data” looks very different
from that of traditional tech industries. Rather than having to solve
problems about the speed and quality of data transfers, scientists must
grapple with bottlenecks in data aquisition, quality assurance, metadata
access, data deposition, and data analysis. While scientists are
relatively well-versed in churning through the process of data
aquisition and analysis, we are not as good at making our workflows
**reproducible**.

There are a number of different ways for data to be big:

  - Volume: the traditional problem

  - Variety: abundance of formats makes wrangling data difficult

  - Velocity: data changes too fast for computer to keep up

### What is data science?

Data science is a cultural term, one that is considered to define an
area of study that represents the intersection of:

1.  Hacking skills

2.  Math and statistics knowledge

3.  Substantive expertise

Data science is the **intersection of all three.** If you are not a
scientist, working on scientific problems, you are not a data scientist.
Data science is *guided by questions*: questions come first; all
methodology is in service of your specific question.

Data science, however, involves much more than just broad classes of
skills. Rather, data scientists must employ a wide variety of
techniques, which themselves deserve more formal treatment by the
scientific community. These include:

1.  Data exploration and preparation

2.  Data representation and transformation

3.  Computing with data

4.  Data modeling

5.  Data visualization and presentation

6.  Science **about** data science

(See Donoho’s “50 years of data science” for a more thorough treatment
of the field and caveats of Data Science.)

### Data science as a process

Wickham’s `tidyverse` depiction is a modern take on data science: he
sees data science as a process, not a static treatment. It involves
importation of data, data cleaning and wrangling (tidying and
transforming), data visualization, modeling, and, finally,
communication. In fact, we now spend the majority of our time cleaning
and preparing data, whereas, in the past, analyses and models took up
the bulk of any scientist’s workday. In the modern area, software has
made statistics fairly fast and simple, while it still struggles with
the sheer size and variety of the data that scientists can now produce.

Today, data visualization and analysis has become a bottleneck. Because
data visualization is time-consuming, it is often the last step taken.
Bad scientists\! Visualization should rather be a primary focus:
visualizing data often provides direction for EDA, and can make
startling trends more apparent earlier.

Types of data repositories:

  - vertically integrated: give us the common denominator; we will
    through out pieces of data that don’t fit (e.g., PBDB\!).

  - unstructured data. “data lake”: toss all of the data “natively” into
    the lake, then perform a “schema on read”: clean the data when you
    read it in; extract data on demand.

Given that most of the data we collect are yet to come, we want to build
a pipeline that is *reproducible* so that we can then come back and
perform similar analyses in the future, with more data. (See **The
Economist**’s “How science goes wrong” on the importance of
reproducibility.)

But reproducibility isn’t just about “morality”: rather, science is more
impactful is researchers can *build on* the work that others have done
in the past. See Peng (2011) <doi:10.1126/science.1213847>.

We must focus on presenation above all things\! Make sure that the code
that you produce is understandable.

*Write code for people. Write data for computers.* (Buffalo 2015)

R is a good language for communicating with people\! The best way to
write code for people is to **not write a lot of code.** (Bless you,
Carl.)

### Logistics

<https://espm-288.carlboettiger.info/policies/>

**git** <http://stevelosh.com/blog/2013/04/git-koans/>

**Advanced R textbook** <http://adv-r.had.co.nz/>

## 25 January 2018: Workflow: GitHub, RMarkdown, Travis

  - See links to *R for Data Science* by Hadley and Garrett for further
    elaboration on RMarkdown (and RStudio’s rmd cheat sheet)

  - Datacamp: accept invitation from Carl?

## RMarkdown

What are the basics of RMarkdown?

  - Learned that you can insert code chunks with `Cmd-Alt-I`.

  - `Ctrl-Shift-1`: fullscreen RMarkdown

  - RNotebook and RMarkdown are the same thing (woo rebranding\!) but
    RMarkdown has slightly more options.

  - Github documents are the primary RMarkdown files we will work with
    during the course

  - `rticles` package allows writing of journal articles in Rmd.

  - We can make presentations in Rmd, too\!

Knuth’s concept of **literate programming**: can we generate
documentation *where we write code*? (see Roxygen documentation later…).
This approach put the focus on documentation *first*, and embedded code
as a secondary product. (Knuth invented “weave”, which was adopted by R
when it was still S, which is why it’s called “sweave”…\!)

Markdown was initially used to wrtie HTML, but has now become a way to
write *anything* by translating that markup into different languages.
Pandoc is used to translate markdown documents written in a number of
languages. (Pandoc was written by a philosophy professor who is still at
Berkeley\!)

Markdown –\> intermediate markdown file (md) –\> Pandoc –\> file of
desired format

`rticles` package allows you to format articles for PNAS, PLoS, etc. You
can do anything in Rmd, it seems–write articles, make presentations,
etc.

## GitHub

  - Used Happy Git with R: <http://happygitwithr.com/> to connect my
    local directory to my GitHub. Hooray\!

  - Tracking previous commits: View –\> Raw –\> can copy and paste
    previous content to get back to previous commit.

  - Can also grab url and download file: add new (old) file, knit, and
    commit

  - Can use git command line: `git checkout <previous hash in URL>
    <filename>`

Thank god for GitHub version control–it keeps you from having to save a
thousand files with the same name and an added ‘final-draft-12’. As
usual, the internet is the best resource for git stuff–a quick google
search will keep ya from banging your head on your keyboard.

### Public vs. private repos:

Public repositories are naked: the public can see everything–your entire
commit history, all the messages you type out in a caffeine-induced
haze, and all the horrible code you hoped to hide.

Private repositories are instead limited to individuals or organizations
(depending on how permissions are set up). If your lab has a github
account (and **any lab can request an organizational account**, as can
students\!), you can make your repos private. It’s up to the
administrators to decide who has access.

  - Settings –\> member priviledges allows you to change which members
    can view, edit, delete, etc.

## Travis

Travis is a CI (continuous integration)–a standard of software
development that checks to ensure that each time you update your code,
you do *not* break it. We can teach Travis to check for style in
addition to whether your program throws errors. This is a good practice,
because it tells you whether your code is **reproducible**. The
.travis.yml file indicates to Travis which tests to run (included in the
“tests” directory in our reops (e.g.
<https://github.com/ds421/climate-sarakahanamoku>)–edit it should you
want to check for other things (e.g., whether you’ve written a nice R
package)\!

In short, Travis helps us write reproducible, agnostic code. We can be
confident that anyone can get the same results that we got on our local
devices.

  - See <https://travis-ci.com/>

  - .travis.yml file looks at code and tests it for reproducibility

  - Travis has both .com and .org modifiers; .com is the home of private
    repos on travis, while .org is the home for public repos on travis

  - Add additional packages to `DESCRIPTIONS` file

Local editing in RMarkdown, GitHub, and Travis are the three
cornerstones of this course.

### Task 1

1.  **Ensure that build of climate repository is passing\!**

<!-- end list -->

  - Update the readme\! Keep your repos tidy and informative.

<!-- end list -->

2.  Continue the climate exercise and try to finish it.
