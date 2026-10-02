---
layout: page
title: Conference Badge Game
html-title: Conference Badge Game
permalink: /badge-game
---

Welcome to our conference badge game! This year each participant's badge contains **one of two symbols**, based solely on their first and last names:

<div align="center" style="margin-bottom: 30px;">
    <img class="width-100 width-max-300px photo" style="margin-bottom: 5px; border: 0;" src="{{ "./images/optimized/badge-game-800x800/CNN.webp" | relative_url }}">
    <img class="width-100 width-max-300px photo" style="margin-bottom: 5px; border: 0;" src="{{ "./images/optimized/badge-game-800x800/RNN.webp" | relative_url }}">
</div>

<span style="font-size: 1.25em; text-align: center; display: block;">
    <span style="letter-spacing: 5px; font-style: italic;">f</span>(firstName, lastName) ∈ {CNN, RNN}
</span>

As in classic machine learning problems, your task is to **collect data** and **discover the unknown mapping function**.
The **first five participants** who correctly predict all the labels for the test set will receive special prizes. 


## / Rules

The rules are simple --- collect as much data as possible and discover the mapping function to accurately predict the labels for the names in the test set. Participants who will succeed with their predictions have a chance to win prizes. If none of the participants solve the puzzle by the end of the conference, the prizes will be drawn among all participants who get the highest number of correct predictions on the test set.
You can **network with other attendees** to collect their names and associated labels or **visit sponsor booths to collect extra data points** that will help you discover the mapping function.

The assigned labels are printed on the back of the badges, so you can ask other participants to show them.

<div align="center" style="margin-bottom: 30px;">
    <img class="width-100 width-max-300px photo" style="margin-bottom: 5px;" src="{{ "./images/optimized/badge-game-800x800/badge-cnn.webp" | relative_url }}">
    <img class="width-100 width-max-300px photo" style="margin-bottom: 5px;" src="{{ "./images/optimized/badge-game-800x800/badge-rnn.webp" | relative_url }}">
</div>

## / Hints

Don't worry if you can't find the pattern right away --- after each day we will provide hints to guide you in solving the mapping function. But remember, the faster you solve the puzzle, the higher are your chances of winning.

- **Hint 1:** Numbers hide behind the letters.
- **Hint 2:** The first letters of the labels (**C**NN, **R**NN) are important.
- **Hint 3 (post winners' list closed):** A beginning follows the end.

## / Submit results

Submit your predictions for the test set names by filling out the form — you can make multiple submissions (under a reasonable limit).

<div align="center" style="margin-bottom: 30px;">
    <a href="https://mlinpl2025-badge-game.paperform.co" class="btn btn-default btn-lg btn-nonactive" target="_blank" disabled><i class="fa-solid fa-list"></i> Submit your predictions</a>
</div>

Submissions are closed.

## / Solution

The label depends only on the letters of your first and last name --- their order and case don't matter.

1. **Clean the name.** Join the first and last name, drop diacritics (e.g. ł → l, ó → o) and keep only the letters A--Z.
2. **Turn letters into numbers.** Each letter becomes its position in the alphabet: A = 0, B = 1, ..., Z = 25.
3. **Measure the distance to C and R** (the first letters of **C**NN and **R**NN) for every letter. The alphabet wraps around like a clock -- *a beginning follows the end* -- so the distance is the shorter way around: e.g. the distance between Z and A is 1, not 25.
4. **Average the distances** over all letters of the name, separately for C and R.
5. **Pick the closer letter.** If the name is on average closer to C, the label is **CNN**; if it is closer to R, the label is **RNN** (a tie goes to CNN).

For example, *Ada Lovelace* → ADALOVELACE has an average distance of 4.36 to C and 8.64 to R, so the label is **CNN**. *Alan Turing* → ALANTURING has an average distance of 7.3 to C and 5.7 to R, so the label is **RNN**.

### / Test set

| Name | Avg. distance to C | Avg. distance to R | Label |
|---|:-:|:-:|:-:|
| Alan Turing | 7.30 | 5.70 | **RNN** |
| Kunihiko Fukushima | 7.29 | 6.53 | **RNN** |
| Kaiming He | 6.00 | 8.56 | **CNN** |
| Mary Shelley | 6.18 | 7.00 | **CNN** |
| Alex Krizhevsky | 5.86 | 7.14 | **CNN** |
| Jürgen Schmidhuber | 6.00 | 7.24 | **CNN** |
| Stanisław Ulam | 7.23 | 5.31 | **RNN** |
| Ada Lovelace | 4.36 | 8.64 | **CNN** |
| Richard Feynman | 5.64 | 7.50 | **CNN** |
| Frank Rosenblatt | 7.40 | 5.47 | **RNN** |
| Ernst Ising | 8.00 | 5.40 | **RNN** |
| Frank Herbert | 6.33 | 6.67 | **CNN** |
| John von Neumann | 8.57 | 5.57 | **RNN** |
| Margaret Hamilton | 7.19 | 6.06 | **RNN** |
| John McCarthy | 6.33 | 6.67 | **CNN** |
| Stanisław Lem | 7.17 | 5.83 | **RNN** |
{: .table .table-condensed}
