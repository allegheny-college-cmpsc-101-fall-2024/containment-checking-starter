# Containment Checking

TODO: Make sure that you delete all of the TODO markers inside of this file and
either remove or rewrite the prompts. When you are finished with this reflection
it should contain professional writing that is suitable for publishing. That
includes removing this paragraph!

## Add Your Name Here

## 1. Source Code

### Describe in detail how the provided source code works

TODO: Write at least one paragraph to explain the provided source code

```python
number_runs = 10
number_repeats = 3
execution_times = timeit.Timer(containment_check_lambda).repeat(
    repeat=number_repeats, number=number_runs
```

### Describe how you implemented the following function

```python
def calculate_average_values(data_list: List[float], data_count: int) -> List[float]:
```

TODO: Write at least one paragraph to explain the source code that you wrote for this function

## 2. Research Report

### Research Questions

TODO: This reflection is a lab report documenting your work to learn about the
worst-case performance of the `in` operator in python.
Clearly state at least three research questions that you want to ask and
answer by using the `containmentcheck` program. You should provide the research
questions in a list with three entries that each start with "RQ" and end with a
question mark. The RQ's you write must be possible to answer with the
`containmentcheck` program and connect to worst-case analysis. Remember,
the worst case occurs when the container does not have a specified value
inside! You may find it helpful to consider following parameters as you think
of research questions.

- The data container: `set`, `list`, and `tuple`
- The size of the data container: small values (e.g., 1 million numbers) to big
  values (e.g., 32 million numbers)
- worst case vs not worst case
- The maximum value of the numbers that are inside of the data container

### Raw Data

TODO: Record at least five examples of program output to demonstrate that
your `containmentcheck` program works correctly and can allow you to empirically
answer your RQs above about the worst-case performance
for searching lists, tuples, and sets. Document and justify your
choice for all of the experiment parameters. Make sure the commands you use
to get the output is included in your explanations. Put the output in fenced-
code blocks.

- First output from running the `containmentcheck` program
- Second output from running the `containmentcheck` program
- Third output from running the `containmentcheck` program
- Fourth output from running the `containmentcheck` program
- Fifth output from running the `containmentcheck` program
- any others needed to answer RQs.

### Processed Data Tables

TODO: Use Markdown to make one or more data tables that summarize your results
from running the `containmentcheck` program in different configurations. You
should organize the data from above in such a way that it connects to your
research questions clearly. Refer to previous labs for examples of Markdown
syntax to make tables.

You may wish to make tables that contain analyzed data, such as averages.
The exact analysis and tables needed here will depend on your RQs.

### Empirical Evaluation

TODO: Provide at least three paragraphs that explain which containment checking
algorithm is fastest, by how much it is faster, and how you knew that it was
faster, referencing the data in the aforementioned command outputs and the data
tables to support your response. You should make sure that you answer each of
the at least three research questions that you posed in a previous section.

TODO: Make sure that your responses explain WHY certain configurations are faster!
TODO: It is NOT sufficient to ONLY explain WHICH configuration is faster!

### Analytical Evaluation

TODO: Using the provided source code for the different containment check
algorithms, your textbook, your experimental results, and any relevant online
resources that you cite in this reflection, define the worst-case time
complexity, using the big-O notation, for the three containment check
algorithms called `containment_check_tuple`, `containment_check_list`, and
`containment_check_set`. You should justify why you picked that complexity.

## 3. Professional Development

TODO: Provide a one-paragraph response that answers these question in your own words.

- What is the most challenging task when designing an experiment to evaluate an algorithm's performance?
- Why is it necessary to perform both an analytical and an empirical evaluation of an algorithm?
- How do the empirical results suggest that you don't yet know the entire story about the performance of containment checking?
