# Algorithmic Problem Solving Bootstrap (NYU)
By Jason Yao

## Description
This is a boilerplate setup for anybody taking CSCI-480: Algorithmic
Problem Solving at New York University, and using **java** as their
programming language (Sorry C++ people).

### What problem this repo is supposed to solve
This repo will contain the framework that'll help bootstrap you
and hopefully enable you to succeed at the class. It contains:

- Automated build & test scripts (homework/recitations and midterm/final formats)
- Clear framework for separation of homework/recitation contests/midterms & finals
- Clear references to 3rd party algorithms/code that've been pre-approved
for course use and are validated as correct.

Note: This assumes a familiarity with the command line and a
*nix system/subsystem. If you aren't, I'd highly recommend you
take the opportunity to read some introductions to the command
line, since it's a speed multiplier in some situations.

If you're using windows, you can register as a [Windows Insider](https://insider.windows.com/), and
get the slow-track builds that contains [Bash for Windows](http://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/).

## Tutorial
### Before the Competition
Say we're about to head into the first recitation competition.
To setup and get ready before the competition (assuming the
repo is already downloaded):
```sh
cp -r bootstrap/ recitations/ex1
cd recitations/ex1
```

At this point, I'd like to recommend you use the tab system in your
terminal client. Make 4 tabs (`CMD` + `t` on macOS) in total, and
label them either with the [title](https://gist.github.com/JasonYao/1270908c0918f048d5433fd3b29ff61e) command, or in your head. *

**Tab A** title: `input`
```sh
title input
cd testing/input
```
**Tab B** title: `answer`
```sh
title answer
cd testing/answer
```
**Tab C** title: `compile`
```sh
title compile
```
**Tab D** tite: `references`
```sh
title references
cd references
```

\* Protip: You can use the `pwd` command
to show your current directory (say your
`recitations/ex1` directory). Then copy and paste the
following to get each of your tabs into the root
directory:
```sh
cd <pwd_output>
```

Open up your IDE (I recommend [IntelliJ IDEA](https://www.jetbrains.com/idea/), which is free for students).
If you use macOS, you can open it in **Tab C** via
```sh
# macOS only
open -a "IntelliJ IDEA" . # Note the period
```

You are now ready to use this speedup testing framwork properly during the competition.

### At the Competition
First things first, let's say that this week we have 6 questions.
The boilerplate comes with 5 identical java start files, and one
[boilerplate one](Main00.java) to copy from. Since we have 1 more question we need
to answer, we can copy the boilerplate file:
```sh
# In Tab C
cp Main00.java Main06.java
```

Now let's say that question 3 is a trivial one that you want to answer first.
Copy the input from the question verbatim (please check if you're missing lines
when copying) into `input-03` in **Tab A**.

Then copy the correct output into `answer-03` in **Tab B**

Now open up Main03.java in your IDE, and start coding!

Once you believe that your solution works, and would like to check it,
simply go to **Tab C** and type (or hit the up-arrow if you've already
used the command before):
```sh
# In Tab C
./compile_and_test <question_number>
# e.g. ./compile_and_test 3
```

This will do a few things:

0.) Compile your code (lets you know if there's any compile errors)

1.) Executes your code & saves the output in `testing/output/output-0<question_number>`

2.) Diff your output against the correct output, and shows what differences
(if any) there are. Running this command and then not getting any output means
that your code generated the correct solution (for the given input set! May not
be true for some edge cases)

Let's assume that we're pretty sure we have the solution then, since it generated
the correct output. We then copy our `Main03.java` code, and paste it into the answer
box on the competition site (make sure to switch the code language to java).

If your answer is correct, then proceed to the next questions via the above process.

If your answer was incorrect, then both take a look through your code to see where you
may have gone wrong, and/or add some additional test & answer cases to test any hidden
edge cases.

## Setup
0.) Download the git repo into a directory called `aps` and go into it
```sh
git clone https://github.com/JasonYao/Algorithmic-Problem-Solving-Base.git aps
cd aps
```

### Setup a New Homework Assignment
Assuming you're at the root of the directory (`aps`)
```sh
cp -r bootstrap/ homework/ex<week_number_here>
# e.g. cp -r bootstrap/ homework/ex4 for week 4's homework

# macOS only
open -a <editor/IDE> <path_to_ex_folder>
# e.g. open -a "IntelliJ IDEA" homework/ex4
```

### Doing a Recitation Competition
Assuming you're at the root of the directory (`aps`)
```sh
cp -r bootstrap/ recitations/ex<week_number_here>
# e.g. cp -r bootstrap/ recitations/ex2 for week 2's competition

# macOS only
open -a <editor/IDE> <path_to_ex_folder>
# e.g. open -a "IntelliJ IDEA" recitations/ex2
```

### Updating/Adding New Reference Code
To add to the reference library when new code,
simply place it in the [references](references/) directory.

### Setting up for midterm/final
Since the midterm/final uses something similar to
the google code jam system instead of the normal one
used in recitation, that means that the setup steps
will be slightly different (please practice before you
start the midterm/final!) *

Assuming you're at the root of the directory (`aps`)
```sh
cp -r special_bootstrap/ <event>
# e.g. cp -r special_bootstrap midterm
# or
# e.g. cp -r special_bootstrap final

# OSX only
open -a <editor/IDE> <path_to_event_folder>
# e.g. open -a "IntelliJ IDEA" midterm
```

\* Note: You can actually use this setup for the actual
[Google Code Jam](https://code.google.com/codejam/) as well!

## Final Thoughts and Tips
### Lectures
In lectures, you normally don't have to code at all, as it's
the explaination of theoretical computational concepts and
algorithms mostly. If you've taken CSCI-310 Basic Algorithms,
this will be basically the same kind of stuff, though with some
broader topics covered than in basic algo.

### Recitations
In recitations, you'll be thrust into a timed (normally 1 hour) [coding competition](https://en.wikipedia.org/wiki/Competitive_programming).
If you're unfamiliar with the setup (like I was), this'll be a bit
of a shock to you. Minutiae details that you may not have thought
about in basic algo will come to haunt you if you've never coded up
the actual algorithm solution (which is why I HIGHLY recommend taking
outside class time to implement your version of the algorithm, so you
can know the limitations of your code better than the [copy-and-paste](references/)
versions).

### Homework
For homework, you'll be assigned a week to solve ~5
programming problems. This will be the same format
as the recitations, and will basically be a more relaxed
version where you can take your time with the problems
instead of being rushed to solve them like in the recitations.

## Licensing
This repository is licensed under the terms of the GNU GPL v3, a version of which may be found [here](LICENSE)
