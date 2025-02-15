
# Containment Checking Engineering Lab

[![build](../../actions/workflows/build.yml/badge.svg)](../../actions/)
![Platforms: Linux, MacOS, Windows](https://img.shields.io/badge/Platform-Linux%20%7C%20MacOS%20%7C%20Windows-blue.svg)
[![Language: Python](https://img.shields.io/badge/Language-Python-blue.svg)](https://www.python.org/)
[![Code Style: Black](https://img.shields.io/badge/Code%20Style-Black-blue.svg)](https://github.com/psf/black)
[![Commits: Conventional](https://img.shields.io/badge/Commits-Conventional-blue.svg)](https://www.conventionalcommits.org/en/v1.0.0/)
[![Discord](https://img.shields.io/discord/872320492936257537?logo=discord)](https://discord.gg/kjah8MFYbR)

## Introduction

This engineering lab invites you to implement and use a program called
`containmentcheck` that conducts an experiment to evaluate the worst-case
performance of containment checking using the `in` operator for different
types of data containers like tuples and lists and sets.

The worst-case performance is observed by intentionally trying to locate
an element that does not exist in a container. For example, if a container
is made to only contain integers up to 100, then searching for 101 will
represent the worst case scenario!

## Learning Objectives

The learning objectives of this assignment are to:

1. Use Git and GitHub to manage source code file changes
2. Use class variables
3. Search for specific number in Pythonic way
4. Design empirical test to capture worst case performance
5. Write clearly about the programming concepts in this assignment
6. Relate algorithmic constructs to time complexity

## Quick Links

- Due date: Check Discord or the
  [Course Materials Schedule](https://github.com/allegheny-college-cmpsc-101-fall-2024/course-materials/blob/main/Schedule.md)
- Policy on
  [Tokens](https://github.com/allegheny-college-cmpsc-101-fall-2024/course-materials#tokens)
- [Token Form for Automatic Extension](https://forms.gle/y9Mz55hQKr84wzvXA)
- Policy for
  [Assignment Evaluation](https://github.com/allegheny-college-cmpsc-101-fall-2024/course-materials#assignment-evaluation)
- Policy for [Assignment Submission](https://github.com/allegheny-college-cmpsc-101-fall-2024/course-materials#assignment-submission).
- [#data-structures Discord channel](https://discord.com/channels/877320365825749002/1274744318124359732)
- [Starter repo](https://github.com/allegheny-college-cmpsc-101-fall-2024/containment-checking-starter)

## Project Goals (Project Overview Below)

This engineering lab invites you to implement and use a program called
`containmentcheck` that conducts an experiment to evaluate the worst-case
performance of containment checking using the `in` operator for different
types of data containers like tuples and lists and sets.

The worst-case performance is observed by intentionally trying to locate
an element that does not exist in a container. For example, if a container
is made to only contain integers up to 100, then searching for 101 will
represent the worst case scenario!

When you run the completed version of the
`containmentcheck` program it will allow you to specify the size of the
container, the maximum value of the integer values stored in the container, the
type of data container, and whether or not the searching algorithm should look
for a value that does or does not exceed the maximum value in the list. If you
configure it correctly, the `containmentcheck` program will total and average
time for using the `in` operator for the automatically generated lists.
Specifically, `containmentcheck` will use the
[timeit](https://docs.python.org/3/library/timeit.html) package to measure the
performance of the `in` operator for different data containers, following one
of the approaches outlined in the article called [measure execution time with
timeit in Python](https://note.nkmk.me/en/python-timeit-measure/). As you
complete this engineering effort you will experimentally evaluate the claims
in the following articles about the best way to determine if a specific value
exists inside of a data container.

- [Membership testing](https://switowski.com/blog/membership-testing)
- [Python speed](https://wiki.python.org/moin/PythonSpeed)
- [Using key in list to check if key is contained in list](https://docs.quantifiedcode.com/python-anti-patterns/performance/using_key_in_list_to_check_if_key_is_contained_in_a_list.html)
- [Why is a set faster than a list in Python?](https://www.quora.com/Why-is-a-set-faster-than-a-list-in-Python)

### Expected Output

After you finish a correct implementation of all the `containmentcheck`'s
features you can run it with the command `poetry run containmentcheck --size
32000000 --maximum 50000000 --approach list --exceed` and see that it produces output
like the following. It is worth noting that your invocation of the program will
likely produce different results than those provided because of the fact that
your laptop may have different software and hardware, and thus different
performance characteristics, than the one used to run `containmentcheck`. With
that said, a finished version of `containmentcheck` should report both the total
and average time for use the `in` operator for the specified data container and
searching approach.

```text
✨ Conducting an experiment to measure the performance of containment checking!
         Type of the data container: list
         Size of the data container: 32000000
         Maximum value for a number in the data container: 50000000
         Should the value to search for exceed the maximum number? Yes

🧮 Total time for running 10 runs in 3 benchmark campaigns: [0.016107587000078638, 0.016178363999642897, 0.016164254000614164]

🧮 Average time for running 10 runs in 3 benchmark campaigns: [0.0016107587000078639, 0.0016178363999642897, 0.0016164254000614164]
```

Finally, don't forget that you can display `containmentcheck`'s help menu and
learn more about its features by typing `poetry run containmentcheck --help` to
show the following output. It is worth noting that all of the parameters to the
`containmentcheck` program, excepting those connected to completion of
command-line arguments or the help menu, are required. This means that the
`containmentcheck` will produce an error if you do not specify the four required
parameters that describe the experiment.

```shell
╭─ Options ─────────────────────────────────────────────────────────────╮
│ --size                             INTEGER          [default: 5]      │
│ --maximum                          INTEGER          [default: 25]     │
│ --exceed            --no-exceed                     [default:         │
│                                                     no-exceed]        │
│ --approach                         [list|set|tuple  [default: list]   │
│                                    ]                                  │
│ --install-compl…                   [bash|zsh|fish|  Install           │
│                                    powershell|pwsh  completion for    │
│                                    ]                the specified     │
│                                                     shell.            │
│                                                     [default: None]   │
│ --show-completi…                   [bash|zsh|fish|  Show completion   │
│                                    powershell|pwsh  for the specified │
│                                    ]                shell, to copy it │
│                                                     or customize the  │
│                                                     installation.     │
│                                                     [default: None]   │
│ --help                                              Show this message │
│                                                     and exit.         │
╰───────────────────────────────────────────────────────────────────────╯
```

Please note that the provided source code does not contain all of the
functionality to produce the output displayed in this section. As the next
section explains, you should add the features needed to ensure that
`containmentcheck` produces the expected output! After implementing a function
that can automatically generate a data container that has random numerical
values inside of it, you will need to create each of the containment checking
functions for all of the supported data containers (i.e., `list`, `tuple`, and
`set`).

Don't forget that if you want to run the `containmentcheck` you must use your
terminal window to first go into the GitHub repository containing this
project and then go into the `containmentcheck/` directory that contains the
project's source code. Finally, remember that before running the program you
must run `poetry install` to add its dependencies, such as Pytest for
automated testing and Rich for colorful output!

### Adding Functionality

If you study the file `containmentcheck/containmentcheck/main.py` you will see
that it has many `TODO` markers that designate the functions you must implement
so as to ensure that `containmentcheck` runs the desired experiment and produces
the correct output. Once you complete a task associated with a `TODO` marker,
make sure that you delete it and revise the prompt associated with the marker
into a meaningful comment. Specifically, you will need to implement the
following Python functions:

- `def generate_random_number(maximum: int, exceed: bool = False) -> int`:
  automatically create a random number starting at zero and going up to the
  `maximum` value. When `exceed` is `true` the function should generate a number
  that is greater than the specified maximum value.

- `def generate_random_container(size: int, maximum: int, make_tuple: bool =
  False) -> Union[List[int], Tuple[int, ...]]`: automatically generate a data
  container that must be either of type `List` or type `Tuple`, ensuring that it
  contains exactly `size` numbers that are never bigger than the specified
  `maximum`.

- `def containment_check_list(thelist: List[int], number: int) -> bool`: use the
  `in` operator to perform containment checking for the provided list.

- `def containment_check_tuple(thetuple: Tuple[int], number: int) -> bool`: use
  the `in` operator to perform containment checking for the provided tuple.

- `def containment_check_set(thelist: List[int], number: int) -> bool`: after
  converting the provided list to a set, use the `in` operator to perform
  containment checking for the set. This function will allow you to
  experimentally evaluate the [conventional
  wisdom](https://docs.quantifiedcode.com/python-anti-patterns/performance/using_key_in_list_to_check_if_key_is_contained_in_a_list.html)
  that a developer can improve the performance of their Python program by
  converting a `list` to a `set` before using the `in` operator.

Ultimately, you should design your own experiment and state and run experiments
to answer your own research questions, focusing on the following key issues:

- The data container: `set`, `list`, and `tuple`
- The size of the data container: small values (e.g., 1 million numbers) to big
  values (e.g., 32 million numbers)
- Whether or not the value that it being searched for is `in` the list
- The maximum value of the numbers that are inside of the data container

## Running Checks

### Helper Tasks

Helper tasks are run in the terminal with the poetry environment activated.
The format of the commands are always `poetry run task xyz`...where `xyz`
is the helper task name.

If you study the source code in the `pyproject.toml` file you will see that it
includes the following section that specifies different executable "helper
task" names like `ruff`, `fix`, `ruffdetails`, etc.

```toml
[tool.taskipy.tasks]
```

If you are in the `objectprocessor` directory that contains the
`pyproject.toml` file, the helper tasks
make it easy to run commands like `poetry run task ruff` to automatically run
the ruff linter designed to check the Python source code in your program
to confirm that your source code adheres to industry standards for formatting.
You can also use the command `poetry run task fix` to automatically reformat the
source code. `poetry run task ruffdetails` will print out detailed linting errors
that point to exactly what ruff views as a linting error. Make sure to examine
the `pyproject.toml` file for other convenient tasks that you can use to both
check and improve your project!

### Gatorgrade

The command `gatorgrade --config config/gatorgrade.yml` will check your work. If
your work meets the baseline requirements and adheres to the best practices that
proactive programmers adopt you will see that all the checks pass when you run
`gatorgrade`. Try to pass as many checks as you can. Missing some checks will only
impact a part of your grade in this Engineering Lab. Note, modifications to the
gatorgrade.yml file are not permitted without explicit instruction.

Don't forget that when you push source code or technical writing to your
GitHub repository for this project, it will trigger the run of a GitHub
Actions workflow. If you are a student at Allegheny College, then running
this workflow consumes build minutes for the course's organization! As
such, you should only push to your repository once you have made
substantive changes to your project and you are ready to confirm its
correctness. Before you push to your GitHub repository, you can still run
checks on your own computer by using Poetry and GatorGrader. You can also
add and commit work locally before pushing it by using git commands in the
terminal: `git add .` and `git commit -m "Commit Message"`.

### Project Reflection

Once you have finished both of the previous technical tasks, you can use a text
editor to answer all of the questions in the `writing/reflection.md` file. For
instance, you should provide the output of the Python program in several fenced
code blocks, explain the meaning of the Python source code segments that you
implemented, and answer all of the other questions about your experiences in
completing this project. A specific goal for this project's reflection is to
ensure that you can explain Python source code that uses the
[timeit](https://docs.python.org/3/library/timeit.html) package to evaluate the
performance of a specific approach to containment checking, as illustrated by
the following code segment. Can you explain this source code?

```python
number_runs = 10
number_repeats = 3
execution_times = timeit.Timer(containment_check_lambda).repeat(
    repeat=number_repeats, number=number_runs
```

### Project Assessment

Since this project is an engineering effort, it is aligned with the
**evaluating** and **creating** levels of [Bloom's
taxonomy](/proactive-learning/blooms-taxonomy/). From the start to the end
of this project you may make an unlimited number of reattempts at submitting
source code and technical writing that meet all aspects of the project's
specification.

## Project Overview

After cloning this repository to your computer, please take the following
steps:

- Use the `cd` command to change into the directory for this repository.
- Specifically, you can change into the program directory by typing `cd containmentcheck`.
- Install the dependencies for the project by typing `poetry install`.
- Run the program in the following fashion:
  - `poetry run containmentcheck --size 5000 --maximum 50000000 --approach list --exceed`
  - Note that this is not the only configuration you should try for your experiment
  - Note that the program will not work unless you add the required source code
  - Refer to the `writing/reflection.md` for details about designing your experiment
- Please note that the program will not work unless you add the required
  source code at the designated `TODO` markers.
- Confirm that the program is producing the expected output described above
- Run the automated grading checks by typing
  `gatorgrade --config config/gatorgrade.yml`.
- You may also review the output from running GatorGrader in GitHub Actions.
- Don't forget to provide all of the required responses to the technical writing
  prompts in the `writing/reflection.md` file.
- Please make sure that you completely delete the `TODO` markers and their
  labels from all of the provided source code.
- Please make sure that you also completely delete the `TODO` markers and their
  labels from every line of the `writing/reflection.md` file.
