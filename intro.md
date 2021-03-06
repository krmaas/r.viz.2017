R
========================================================
author: Kendra Maas
date: Jan 12, 2017
autosize: true

Why R?
========================================================
incremental: true
- FREE
- It is a Language
    * Can be added to by anyone
    * Reproducible
- *Nearly* the only data management, data cleaning, analysis, visualization, etc software you need
    * Size limitations apply
- Packages play well together
- Becoming (is?) default stats language for much of science

Why Data Analysis
====================

![Data analysis cycle, Wickham 2011](../data.analysis.cycle.Wickham2011.jpg)


What are we aiming for?
===============

![Venn diagram of Data Science](../data.science.venn.png)

My sources for this workshop
==================

- R classes that I've taken
    * www.zoology.ubc.ca/~schluter/R/
    * www.coursera.org/course/rprog
    * jennybc.github.io/2014-05-12-ubc/ 
    * Data Carpentry and Software Carpentry workshops, borrowing heavily
    * http://courses.had.co.nz.s3-website-us-east-1.amazonaws.com/12-rice-bdsi/  didn't take it but wish I could've
- Numerical Ecology with R, Legendre 2012
- User groups (and blogs, usually just google)
    * R-sig-ecology
    * Stackoverflow


=================

# Write code for humans,
# write data for computers

- Vince Buffalo

## Your most important collarborator is future you

- unknown

Why Scientific Programing
===============
incremental: true

(from Software Carpentry)
- A program is just another piece of lab equipment
- Programing is a human activity
- Little pieces loosely joined
- Let the computer repeat it
- Paranoia makes us productive
- Better algorithms beat better hardware
- Reproducible Analysis needed for Reproducible Science
-

Don't repeat yourself or others
============
incremental: true

- Automate common actions by saving simple blocks of code into scripts
    + A script is a set of commands *organized* in a single file
    + A script is the basic unit of scientific programing
- Document what you've done
- Save time because you can reuse it
- Use scripts to explore new ideas, be comfortable writing, altering, and throwing bad ones away

Use version control
================
incremental: true

Really, it will make your life easier

- Checkpoint you code
- Allows creativity with less worry about losing work
- Does part of the documentation work for you

Document your code
==============
incremental: true

- As you write, document for your future self
- When you have a functional bit of code
    - Write a read-me, even if it's just a few lines at the top of the script
    - Clean up the trial code that didn't do what you wanted (remember it's still in git)
- If you can't describe what a script/code does, consider rearranging or splitting the code


Warnings
=================
incremental: true

- Names matter
- Case matters
- Typos cause 99.95% of beginner "bugs" ("statistic" completely made up)
- Don't make little excerpts of your data, keep it whole and subset in R

![](../lego.png)


