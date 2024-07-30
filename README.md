# rl-picker.github.io

## Overview

This repository holds the source code of the official interactive website [rl-picker.github.io](https://rl-picker.github.io) for the paper [**"How to choose a reinforcement-learning algorithm"** (Bongratz et al., 2024)](https://arxiv.org/search/?searchtype=author&query=Bongratz%2C+F).

## Contributing

### Adding an algorithm
We welcome additions to the list of algorithms. To add an algorithm to the list, please email us its properties such as "off-policy".

### Modifying the rules
Here is an example how to set the status of `"Policy-based"` methods to `"rejected"` if episodes are long (`"durationLong"`):
```
  if (document.getElementById("durationLong").checked) {
    rejectOrDisfavor("Policy-based", "rejected", "Policy-based methods without a learned critic are probably not suited for long episodes since updating parameters only after completed episodes is often inefficient if episodes are long and even impossible for online learning in continuing tasks.");
  }
```

### Software design decisions
If you want to suggest refactoring, please consider that our priorities are:
- code that is easy to understand, maintain, and run
- speed
- privacy
- support for old browsers for important functionality

and we therefore prefer:
- no interactive communication with servers, no server-side code generation
- no need to install anything, no dependencies on third-party libraries
- static HTML for the table of algorithms
- interactivity through CSS (e.g. `:hover`) when possible rather than JS
- no polyfills especially for unimportant functionality
- embedded scripts and styles instead of dependencies between separate files

