# Practice-lab-4-answer

# AI Lab 4 — Answers to Remaining Questions

## Section 12: Task 2 — Different Board Sizes

**Question: Does the same board size always produce the same result?**

**Answer:**

No, the same board size does not always produce the same result. Hill-Climbing starts with a random initial state, so every run can produce different results.

Sometimes the algorithm finds a valid solution with zero conflicts. Other times, it stops at a local maximum with some conflicts remaining.

The number of iterations can also change between runs.

**Experiment Results:**

Fill in this table using the actual output from Google Colab.

| N | Run | Final Conflicts | Iterations | Solved? |
|---|---|---|---|---|
| 4 | 1 | ___ | ___ | ___ |
| 4 | 2 | ___ | ___ | ___ |
| 8 | 1 | ___ | ___ | ___ |
| 8 | 2 | ___ | ___ | ___ |
| 8 | 3 | ___ | ___ | ___ |
| 10 | 1 | ___ | ___ | ___ |
| 10 | 2 | ___ | ___ | ___ |
| 10 | 3 | ___ | ___ | ___ |

---

## Section 16: Task 3 — Comparing Both Algorithms

**Q1. Did basic Hill-Climbing find a solution in every run?**

**Answer:**

No, basic Hill-Climbing does not always find a solution. Sometimes it gets stuck at a local maximum where no better neighboring state is available.

**Q2. Did Random-Restart Hill-Climbing improve the results?**

**Answer:**

Yes, Random-Restart Hill-Climbing generally improves the chances of finding a solution. It starts new searches from different random initial states instead of depending on only one starting state.

**Q3. How many restarts were needed to find a solution?**

**Answer:**

The number of restarts depends on the random initial states. The algorithm continues restarting until it finds a solution or reaches the maximum restart limit.

I recorded the actual number of restarts from my Google Colab output.

**Q4. Did any random-restart experiment reach its restart limit without finding a solution?**

**Answer:**

This depends on the experiment results. If the algorithm does not find a solution within 100 restarts, it reaches the restart limit and returns the best state it found.

**Q5. Why can Random-Restart improve the probability of success without guaranteeing success within a fixed number of attempts?**

**Answer:**

Random-Restart uses different starting states, giving the algorithm more opportunities to find a solution. However, every attempt can still fail. Therefore, it increases the probability of success but cannot guarantee a solution within a fixed number of attempts.

---

## Section 17: Lab Questions

### Question 1

**What is the purpose of the evaluation function in Hill-Climbing?**

**Answer:**

The evaluation function measures how good a particular state is. In the N-Queens problem, it counts the conflicts between queens. It helps Hill-Climbing select a better neighboring state.

### Question 2

**Why is an evaluation score of zero the best result in our N-Queens implementation?**

**Answer:**

The evaluation score is the negative number of conflicts. A score of zero means there are no conflicts between queens. Therefore, all queens are safe, and the puzzle is solved.

### Question 3

**What is the difference between a local maximum and a global maximum?**

**Answer:**

A local maximum is a state that is better than all its neighboring states, but it may not be the best state in the entire search space.

A global maximum is the best possible state in the entire search space.

### Question 4

**Why can basic Hill-Climbing stop without finding a solution even when a solution exists?**

**Answer:**

Basic Hill-Climbing can stop when none of the neighboring states has a better evaluation score. It may reach a local maximum that is not the actual solution, even though a correct solution exists somewhere else.

### Question 5

**Does reaching a local maximum always mean that the algorithm has failed? Explain.**

**Answer:**

No. A local maximum can also be the global maximum. If the state has zero conflicts, it is a valid solution. However, if conflicts remain, the algorithm has stopped without solving the problem.

### Question 6

**For N = 8, how many neighbors does each state have in our implementation?**

**Answer:**

Each state has N × (N - 1) neighbors.

For N = 8:

8 × (8 - 1) = 8 × 7 = 56

Therefore, each state has 56 neighbors.

### Question 7

**What does the evaluation-score graph tell you about the behavior of Hill-Climbing?**

**Answer:**

The graph shows how the evaluation score changes during the search. The score increases when the algorithm moves to a better state. It never decreases during an accepted move. When no better neighbor is available, the algorithm stops.

### Question 8

**Explain probabilistic completeness in your own words.**

**Answer:**

Probabilistic completeness means that the probability of finding a solution gets closer to 100% as the number of independent search attempts increases, provided that each attempt has a non-zero chance of finding a solution.

### Question 9

**Why does Random-Restart Hill-Climbing improve the chance of finding a solution?**

**Answer:**

It improves the chance of success because it starts the search from different random states. If one attempt gets stuck at a local maximum, another attempt may find a better path to the solution.

### Question 10

**Does probabilistic completeness guarantee that a solution will be found within 100 restarts? Why or why not?**

**Answer:**

No. Probabilistic completeness does not guarantee success within 100 restarts. It only means that the probability of finding a solution increases as the number of attempts increases, under the required assumptions.

---

## Section 18: Extension Task — N = 20

**Answer and Observations:**

For this experiment, I used a board size of 20 queens and compared basic Hill-Climbing with Random-Restart Hill-Climbing.

The results depend on the random initial state and the number of restarts.

I recorded the following information from my experiment:

| Measurement | Basic Hill-Climbing | Random-Restart Hill-Climbing |
|---|---|---|
| Final conflicts | ___ | ___ |
| Iterations | ___ | Not applicable |
| Restarts | 1 | ___ |
| Solution found? | ___ | ___ |

**Discussion:**

Basic Hill-Climbing uses only one random initial state. It may find a solution or stop at a local maximum.

Random-Restart Hill-Climbing performs multiple searches from different initial states. It usually has a better chance of finding a valid solution.

As the number of queens increases, the search space becomes larger. The initial state also affects how many conflicts must be removed.

Therefore, Random-Restart can be more useful for finding solutions to larger N-Queens problems.
