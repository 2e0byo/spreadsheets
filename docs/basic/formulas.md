## Nomenklatura

Formulas are, in fact, functions.  The precise implementation varies with each
spreadsheet package, but the basic idea is to write something like

```
=Sum(A1:A7)
```

in a cell.  This sets the cell to the result of evaluating the  *function* `Sum`
with the values of the cells in the range `A1` to `A7`.

In general these function are called formulas, which is in my opinion unduly
confusing.  In this course we will use the term 'formula' to refer to 'writing
stuff in the formula bar', and 'function' to refer to individual statements like
`Sum()` or `If()`.

## Conditionals and Booleans

Consider the following instruction:

> count every cell bigger than 5 as a major outgoing, and every cell smaller as
> a minor outgoing.

How might you implement it?

The criteria 'bigger than 5' could be expressed `>5`.  The element `>5` is
*true* in some cases (when the cell is greater than 5) and *false* in others
(when it isn't).  It might be undefined or erroneous in other cases (when the
cell contains "I am a title!!!").

We call things like `>5` *conditionals*, and we think of them as 'evaluating' to
a 'boolean value'.  In other words, when you 'work out' `>5` you 'get' the
values 'true' or 'false'.  These are called *Booleans* (because they are the
components of *Boolean Logic*, named after a Mr. *Bool* who invented it for the
fun of it, long before we actually applied his theorems to real physical computers.)

!!! Note

    Booleans like 'true' and 'false' are not the only things which can be true or
    false, however!  Some other things are 'falsy', like `0`, and some other things
    are truthy, like `This cell has text in it`.  Exactly what is truthy and falsy
    depends on the spreadsheet package.  You rarely need to think about this,
    but it can be useful when you want to do things like 'count all cells which
    have *something* in them'.  You might find that `if(A1, ...` is true when
    `A1` has anything in it except `0` or `false`, which might be what you want.


## International Functions

Every spreadsheet package has a different set of functions.  However there is a
kind of defacto standard embracing at least the following:

| Function                   | Description                                                                    |
|----------------------------|--------------------------------------------------------------------------------|
| `Sum`                      | add up all arguments passed                                                    |
| `Average`                  | compute the arithmetic mean of all arguments                                   |
| `Count`                    | count the number of arguments.                                                 |
| `Round(number, places)`    | round `number` to `places` places                                              |
| `Ceiling`                  | round *up*                                                                      |
| `If(cond, true, false)`    | if condition is true, return the value of true, else return the value of false |
| `Countif(range, criteria)` | return the number of cells in `range` which satisfy `condition`                |
| `Max`                      | return the max of all arguments passed                                         |
| `Min`                      | return the min of all arguments passed                                         |

If you find yourself writing a long and complicated bunch of nested formulas,
like

```
=If((Sum(A1:A6)/Count(A1:A6)) > $B$7, ((Sum(A1:A6)/Count(A1:A6))), $B$7)
```

You might want a simpler builtin function, like:

```
=Max(Average(A1:A6), $B$7)
```

Keep the documentation open somewhere when trying.

## Chaining Functions

As we have already shown, you can put functions within each other.  The
spreadsheet will evaluate the innermost function first and keep moving out until
it has got one value.  However you should avoid doing this if possible:

- It's confusing and hard to read.
- It's easy to end up with one bracket too few (or to many).  It might still
  work, and do the wrong thing!
- You will likely get a cryptic error message if it fails and have a hard time
  working out what went wrong.
  
Rather, store your intermediate values in *properly labelled* columns or rows.
You can always hide them in them in your final output.
