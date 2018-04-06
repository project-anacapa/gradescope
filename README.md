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

# Converting a C++ assignment based on tddFuncs.h

Some CS16/24/32 assignments are based on a homegrown TDD library for C++ that consists of two files: `tddFuncs.h` and `tddFuncs.cpp`.    

The repo [gradescope-cpp-unit-test](https://github.com/project-anacapa/gradescope-cpp-unit-test) contains versions of those files that can typically be dropped in as replacements for the originals.  

Doing so adds Gradescope support for those assignments, because the new versions generate a `results.json` file (or add into an existing one) as a side-effect of running the unit tests.

In general, the process to convert an existing assignment consists of:

1. Replace `tddFuncs.h` and `tddFuncs.cpp` with the ones from [gradescope-cpp-unit-test](https://github.com/project-anacapa/gradescope-cpp-unit-test).
2. Add `-I/usr/include/jsoncpp -std=c++11` to the `CXXFLAGS` 
3. Add `-ljsoncpp` to each link step either directly, or via `LDFLAGS`
4. Try `make clean` and `make` to ensure it compiles
5. Try running the tests to see if you get a `results.json` file.
