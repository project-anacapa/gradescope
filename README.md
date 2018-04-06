# gradescope

A starting point for learning about Gradescope autograding, intended for UCSB CS department faculty and TAs migrating from UCSB's submit.cs

# What is Gradescope Autograding

Gradescope's main product offering is a web-based tool for grading pencil/paper exams and homework, but that is <b>not what this article is about</b>.

Recently, Gradescope also introduced an autograder option that is in the same space as UCSB's home-grown submit.cs ([website](https://submit.cs.ucsb.edu), [source code](https://github.com/ucsb-cs/submit)) but offers a more robust and flexible infrastructure for building auto-graded assignments.

# How does Gradescope Autograding work (high level description)

At a high level, making an autograded assignment on Gradescope is quite simple: you create a .zip file with a certain format, and you upload it to the Gradescope website.

From there, students can access the Gradescope website to submit their code.    There are also options for submitting directly from a private git repository.

# Repos that may help

| Repo | Description |
|-------|-------------|
| https://github.com/project-anacapa/gradescope-simple-template-draft      | Script to help you setup `autograder.zip` that connects to github |
| https://github.com/project-anacapa/gradescope-cpp-unit-test      | A template for a C++ autograded assignment |
