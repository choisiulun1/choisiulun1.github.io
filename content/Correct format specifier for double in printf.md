---
tags: [C,stackoverflow]
aliases: [Argument Promotion]
---
- `"%f"` is the (or at least one) correct format for a double. There _is_ no format for a `float`, because if you attempt to pass a `float` to `printf`, it'll be promoted to `double` before `printf` receives it[^1]. `"%lf"` is also acceptable under the current standard -- the `l` is specified as having no effect if followed by the `f` conversion specifier (among others).

- Note that this is one place that `printf` format strings differ substantially from `scanf` (and `fscanf`, etc.) format strings. For output, you're passing a _value_, which will be promoted from `float` to `double` when passed as a variadic parameter. For input you're passing a _pointer_, which is not promoted, so you have to tell `scanf` whether you want to read a `float` or a `double`, so for `scanf`, `%f` means you want to read a `float` and `%lf` means you want to read a `double` (and, for what it's worth, for a `long double`, you use `%Lf` for either `printf` or `scanf`).

## What is Prototype 
- ![[Default argument promotions in C function calls#^a32450]]

Reference Read : [[Default argument promotions in C function calls]]

>https://stackoverflow.com/questions/4264127/correct-format-specifier-for-double-in-printf

[^1]: C99, §6.5.2.2/6: "If the expression that denotes the called function has a type that does not include a prototype, the integer promotions are performed on each argument, and arguments that have type float are promoted to double. These are called the default argument promotions." In C++ the wording is somewhat different (e.g., it doesn't use the word "prototype") but the effect is the same: all the variadic parameters undergo default promotions before they're received by the function.