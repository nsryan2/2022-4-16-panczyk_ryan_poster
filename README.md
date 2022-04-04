# Purpose of this Repository

*This template is adapted, with permission, from 
[2019-chee-wm-poster](https://github.com/arfc/2019-chee-wm-poster).*

This repository is intended as a template to standardize and ease the initialization process for posters. 
While this template is geared towards an ARFC Member's poster, it can be adapted 
to any individual's needs.


# ARFC Poster Manual

Follow the guidelines [here](http://arfc.npre.illinois.edu/manual/guides/writing/poster/)
to make a poster.


# How to Use this Template

This repository serves as a template, which means that you can generate an exact copy of it 
without forking, and will exist separate from the template. Learn how to create a repository from a 
template 
[here](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template).


# Adding Citations
To cite something you have to first add a citation to the bibliography.bib file in your local directory.

## Format for a citation in the bibliography file:
The abstract and poster .bib files have several examples of citations in them, feel free to add and 
adapt them as you see fit to the information you wish to provide.

## Adding a citation tag to your content:

    This sentence is used as an example citation call ~\cite{call_tag}.

An important note is that the citation is made with what the example called "call_tag." The first line 
in the example bibliography.bib code contains this tag, and connects the content to the Reference 
section that will be generated in the document.


# Adding an Acronym:
There is a file called acros, which contains a list of acronyms already. If you 
would like to add an acronym of your own, simply add a new line with the format:

`\newacronym{call}{output}{What the acronym stands for}`

The element in {call} will be what you type to use the acronym, whereas {output} will be what 
compiles for every use after the first time you call the acronym.

# Using an Acronym:
This process of adding and using an acronym may seem tedious, but if you call the acronym every 
time you wish to use it, LaTex will make sure it is defined. Meaning the first time you use it, the 
acronym will be attached to its meaning, and that every subsequent use is of the acronym itself.

To call an existing acronym, all you have to do is insert:
`\gls{call}`
to your code.

For the plural version of an acronym, you can use:
'\glspl{call}'

For example, you can create the acronym ANS.

`\newacronym{ANS}{ANS}{American Nuclear Society}`

Then, when you go to use it in your poster or abstract, the following code:

    \gls{ANS} is the premier organization for those that embrace the nuclear sciences 
    and technologies for their vital contributions to improving people’s lives and 
    preserving the planet.

    \gls{ANS} membership is open to all and consists of individuals from all walks of 
    life; including engineers, doctors, students, educators, scientists, soldiers, 
    advocates, government employees, and others.

will output:

    The American Nuclear Society (ANS) is the premier organization for those that 
    embrace the nuclear sciences and technologies for their vital contributions to 
    improving people’s lives and preserving the planet.

    ANS membership is open to all and consists of individuals from all walks of life; 
    including engineers, doctors, students, educators, scientists, soldiers, 
    advocates, government employees, and others.
    
If you were to then add another reference to the acronym ANS before what was the first use, that addition would output `The American Nuclear Society (ANS)` and every subsequent entry would output `ANS`.


# Referencing Tables and Figures

When you create a figure or a table, there is a line (which is included in the examples) 
that creates a label. To reference your figures and tables later in the document, include `fig:` (for 
figures) or `tab:` (for tables) before the name inside the label. Later, when you wish to reference that 
figure or table, you can use `\ref{fig:name}` or `\ref{tab:name}`. These elements will output 
the numbered position that the figure or table appears in relative to other figures.

For example: 
    `\ref{fig:name_of_figure1}` will output `[1]` for the first figure, and clicking on it will bring 
    you to that figure). 

Similar to using acronyms, this is feature will help to keep track of each figure or table.


# How to Initialize the Abstract or Poster

After you have cloned this repository and added your content to the abstract or poster:

Enter the abstract or poster folder and run the command
`make {insert type here}`


For pdf, insert `all-via-pdf` or `all`.

For dvi, insert `all-via-dvi`.

For epub, insert `epub`.

For zip, insert `zip`.


*Note: Do not include the {} from the make command line, replace the whole {insert type here} text with the command corresponding to the correct file type.*

*Ex: To make as a pdf, the full command should be: `make all-via-pdf`*

## To clean your local directory run:

`make clean` or `make realclean`
