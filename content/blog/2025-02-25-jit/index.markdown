---
title: "Just-In-Time: A quick guide using jit with Python"
author: "Cecina Babich Morrow"
date: "2025-02-25"
categories: ["Python"]
tags: ["Python"]
subtitle: 'Speeding up your code in a single line (give or take).'
summary: 'Using jit with Python.'
image:
  placement: 1
  caption: ''
  focal_point: ''
  preview_only: false
projects: []
draft: true
---

# Inspiration for this post

Last June, at an annual retreat for my PhD program ([Compass Away Day](https://compass.blogs.bristol.ac.uk/2024/08/21/compass-away-day-2024/)), [Ed Davis](https://compass.blogs.bristol.ac.uk/students/ed-davis/) gave a talk about a magical way to speed up your Python code in a single line. i blissfully forgot about this until the fall, when I was facing a daunting 3+ *days* of run-time for my code. I heard Ed's voice in my head (probably not a good sign of my sanity in the PhD thus far) and latched onto it as my hope for salvation.

# JIT

The magic solution? ✨JIT✨

JIT stands for "just-in-time", referring to compiling computer code while the program is executed. It sits in between ahead-of-time (AOT) compilation and interpretation.

AOT compilation refers to when a programming language is compiled into a (typically lower-level) language before the program is executed. For example, when coding in C++, you need to compile the human-readable C++ code into machine code, which can then be executed to run your program. On the other end of the spectrum, interpreted languages such as Python and R have an interpreter that reads the code line by line, converts it to machine code, and executes it then and there.

JIT aims to be the best of both worlds, by combining the speed of compiled code with the ease of writing interpreted code. JIT compilation occurs after the program has started (as opposed to AOT) and compiles the 

# Numba

## When might Numba help?








