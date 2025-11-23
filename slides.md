---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
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
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

# What is Advent of Code?

A series of programming puzzle challenges held every
year in December

- 📅 Running every year since 2015
- 🌟 500 puzzles released so far
- 🆓 Free (as in beer) to play
- 🛠 Use whatever languages and tools you like

[https://adventofcode.com](https://adventofcode.com)

---
layout: two-cols
---

# What is Brendan?

- A (vaguely) humaniform carbon-based life form who likes programming.
- Solved all 500 AoC puzzles released to date
- Even managed to rank in the top 1000 on the global leaderboard for a few of
  the puzzles in 2014

::right::

<v-click>
    <div style="padding: 16px;">
        <img src="./stars.png" alt="500 stars" />
    </div>
</v-click>

<v-click>
    <div style="padding: 16px;">
        <img src="./times-2014.png" alt="personal times for 2014" />
    </div>
</v-click>

---

# How does it work?

- During the challenge, a new puzzle is released each day at midnight US EST (4
  pm in Canberra)
- All puzzles remain open to complete at any time
- Each puzzle has a text description of the problem, an explanation of the
  rules, and an example input
- Log in with your profile to get access to your randomised puzzle input 
- Use whatever languages and tools you like to solve the problem
  - But don't use AI, that sucks 🤖🙅‍♂️
- Submit the correct answer to get a ⭐ and reveal Part Two
- Part Two has some kind of twist that makes it a lot harder
- Submit the correct answer for Part Two to get a second ⭐ 

---
layout: two-cols
---

# Who is it for?

- People with some programming experience
- Computer science background not required (but it does help)
- High-spec hardware not required
  - All puzzles solvable in <15s on basic commodity hardware
  - (although I was occasionally too stupid to find a fast solution)

::right::

<div style="padding: 16px;">
    <img src="./stats-2024.png" alt="Stats for 2024" />
</div>

---

# What are the puzzles like?

- Christmas themed 🎄
- Generally increasing in difficulty each day
  - Part Two is usually a step up from Part One
- Each puzzle is fully stand-alone (usually)
- Lots of different problem types, but some common features are
  - Text parsing
  - Data structures
  - Grids and geometry
  - Graphs (not 📊, the other kind of graph)
  - Trees (not 🌲, the other kind of tree)
  - Pathfinding
  - Combinatorics
  - Recursion

---

# What language to use?

## Python, obviously

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
layout: image-right
image: ./third-place.jpg
---

# What changed in 2025?

- Number of puzzles reduced from 25 to 12
- Global leaderboard shut down
  - Bad actors and AI abusers ruined it for everybody
  - Private leaderboards still allowed

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
    <img src="https://github.com/direvus/adventofcode/raw/main/vis/y2019d15.gif" />
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
