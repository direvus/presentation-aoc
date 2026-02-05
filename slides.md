---
# try also 'default' to start simple
theme: seriph
background: advent-interactive-bg.png
# some information about your slides (markdown enabled)
title: "Advent of Code: an introduction and a Python toolkit"
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# duration of the presentation
duration: 35min
---

# Advent of Code

## An introduction + a Python toolkit

<!--
Hi everyone, and welcome to my talk about Advent of Code.

I'm going to give an overview about what Advent of Code is, who
it's for and hopefully give you a sense about whether it's your jam.

Then, I'm going to give a quick tour through the Python toolkit that I've built
up during my time with Advent of Code, which you are very welcome to use for
your own solutions, or take as inspiration to construct your own toolkit.
-->

---
transition: fade-out
layout: two-cols
---

# What is Advent of Code?

A series of programming puzzle challenges held every
year in December

<v-clicks>

- 📅 Running every year since 2015
- 🌟 524 puzzles released so far
- 🆓 Free (as in beer) to play
- 🛠 Use whatever languages and tools you like
- 👍 It's awesome

</v-clicks>

[https://adventofcode.com](https://adventofcode.com)

::right::

<img src="./aoc-2025.png" alt="AOC front page for 2025" />

---
layout: two-cols
---

# What is Brendan?

<v-clicks>

- A (vaguely) humaniform carbon-based life form who likes programming.
- Solved all 524 AoC puzzles released to date
- Even managed to rank in the top 1000 on the global leaderboard for a few of
  the puzzles in 2024

</v-clicks>

::right::

<v-click at="2">
    <div style="padding: 16px;">
        <img src="./stars.png" alt="524 stars" />
    </div>
</v-click>

<v-click at="3">
    <div style="padding: 16px;">
        <img src="./times-2014.png" alt="personal times for 2014" />
    </div>
</v-click>

---

# How does it work?

<v-clicks depth="2">

- During the challenge, a new puzzle is released each day at midnight US EST (4
  pm in Canberra)
- All puzzles remain open to complete at any time
- Each puzzle has a text description of the problem, an explanation of the
 rules, a small example input, and the answer you should get for the example input.
- Log in with your profile to get access to your personalised puzzle input 
- Use whatever languages and tools you like to solve the problem
  - But don't use AI, that sucks 🤖🙅‍♂️
- Submit the correct answer to get a ⭐ and reveal Part Two
- Part Two has some kind of twist that makes it a lot harder
- Submit the correct answer for Part Two to get a second ⭐ 

</v-clicks>

---
layout: two-cols
---

# Who is it for?

<v-clicks depth="2">

- People with some programming experience
- Computer science background not required (but it does help)
- High-spec hardware not required
  - All puzzles solvable in <15s on basic commodity hardware
  - (although I was occasionally too stupid to find a fast solution)

</v-clicks>

::right::

<div style="padding: 16px;">
    <img src="./stats-2024.png" alt="Stats for 2024" />
</div>

---

# What are the puzzles like?

<v-clicks depth="2">

- Christmas themed 🎄
- Difficulty generally increasing each day
  - Part Two is usually a step up from Part One
- Each day is fully stand-alone *
- Explanations are well-written and very thorough
- Beautiful ASCII art on the Advent Calendar page
- Fun little hover titles hidden through the text

</v-clicks>

---

# What are the puzzles like?

Many different problem types, but some recurring features:

<v-clicks depth="2">

- Text parsing
- Data structures
- Grids and geometry
- Graphs (not 📊, the other kind of graph)
- Trees (not 🌲, the other kind of tree)
- Pathfinding
- Combinatorics
- Recursion

</v-clicks>

---

# What language to use?

<v-click>

## 🐍 Python, obviously

</v-click>
<v-click>
    <p>
        Seriously though, Python is the most popular choice.
    </p>
    <p>
        Rust is gaining a lot of ground lately too.
    </p>
    <div>
        <img src="./language.png" alt="Popularity of languages in 2024" width="50%" />
    </div>
    <p>
        Source: <a href="https://jeroenheijmans.github.io/advent-of-code-surveys/">https://jeroenheijmans.github.io/advent-of-code-surveys/</a>
    </p>
</v-click>

---
layout: two-cols
---

# What changed in 2025?

<v-clicks>

- Number of puzzle days reduced from 25 to 12
- Global leaderboard shut down
  - Private leaderboards still allowed

</v-clicks>

<v-click>

## How come?

Bad actors and AI abusers ruined it for everybody

</v-click>

::right::

<v-click>
    <div style="padding: 16px;">
        <img src="./third-place.jpg" alt="Third place" />
    </div>
</v-click>
---

# Tips?

<h2>Don't get discouraged</h2>
<p>Some of these puzzles are genuinely *super* hard</p>

<v-click>
  <h2>Explore the Standard Library</h2>
  <p>Loads of very helpful modules are already built right into Python</p>
</v-click>

<v-click>
  <h2>Check out the subreddit</h2>
  <p>Mostly a very positive community of players</p>
</v-click>

<v-click>
  <h2>Have fun with it</h2>
  <p>Try out a new technique, or a library or even a whole language, or make a
  cool visualisation</p>
</v-click>

---
layout: image-right
image: ./qr-code.png
---

# My toolkit

[https://github.com/direvus/adventofcode/](https://github.com/direvus/adventofcode/)

- Written in Python, for Python
- Interactive terminal application

![Screenshot of terminal app](./advent-interactive.png)

---
layout: two-cols
---

# How to use the toolkit

1. Select your year and day
2. The app will create a new code file from the skeleton
3. Paste in the example input from the AoC puzzle page
4. Open the code file for the day, and get hacking
5. Test your code against the example input
6. Load your actual puzzle input in
7. Run your code against the actual input
8. Submit your answer on the AoC puzzle page

::right::

<div style="padding-left: 32px;">
    <img src="./test-session.png" alt="test session" width="75%" />
</div>

---
lines: true
---

# Skeleton

```python
"""Advent of Code _YEAR_

Day _DAY_: _TITLE_

https://adventofcode.com/_YEAR_/day/_DAY_
"""
import logging  # noqa: F401

from util import timing


def parse(stream) -> str:
    return stream.readline().strip()


def run(stream, test: bool = False):
    with timing("Part 1"):
        parsed = parse(stream)
        result1 = 0

    with timing("Part 2"):
        result2 = 0

    return (result1, result2)
```

---

# Setting up

```sh
# Clone the repo, then:
cd adventofcode
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

🗑 Delete my solutions before you begin!

```sh
rm -rf y2*
```

🍪 Set up your session cookie

```sh
# Copy the value of the cookie from your browser, then:
cat > .session
# <Paste>
# <Ctrl-D>
```

<!--
You are most welcome to copy some or all of my repository, but make sure that
you delete all of my solution code before you begin! Otherwise, you'll just be
using my solutions, and what's the point of that.

You'll also probably want to set up your session cookie, so that the tool can
automatically download your actual puzzle inputs for you. You can find your
session cookie in your browser's developer tools, once you're logged into the
AoC website. Then just dump the value of the session cookie into a file named
`.session`, at the top level of your repo.
-->

---

# Extras

Utility modules

- assembly.py
- grammar.py
- grid.py
- linkedlist.py
- matrix.py
- spans.py
- visualise.py

---

# Visualisations

- Completely optional
- Fun and informative

<div style="margin: 16px auto;">
    <img src="./y2019d15.gif" />
</div>

<!-- Making visualisations is not formally part of the AoC challenge, but is
fun, and sometimes it can help you to understand your solution better.

My repo includes a utility module to assist in building visualisations
frame-by-frame, inline with your solution code. On the slide you can see an
example of a visualisation I made for one of the puzzles, and there are more
examples in the README of the repo.
-->

---

# Links and contacts

## Advent of Code

- [https://adventofcode.com](https://adventofcode.com)
- [r/adventofcode](https://www.reddit.com/r/adventofcode/)

## Me

- Email -- [direvus@gmail.com](mailto:direvus@gmail.com)
- My GitHub -- [https://github.com/direvus/](https://github.com/direvus/)
- The toolkit repo -- [https://github.com/direvus/adventofcode/](https://github.com/direvus/adventofcode/)
- Source code for these slides -- [https://github.com/direvus/presentation-aoc/](https://github.com/direvus/presentation-aoc/)
