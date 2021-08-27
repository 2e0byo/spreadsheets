## Operators

The standard algebraic operators are available.

| operator       | written |
|----------------|---------|
| Addition       | `+`     |
| Subtraction    | `-`     |
| Multiplication | `*`     |
| Division       | `/`     |
| Exponent       | `^`     |

!!! tip
    To use any kind of operator in a cell, you need to start with `=`.
    
## References
You reference the value of another cell by writing its cartesian address (e.g.
`A1`). You reference a *range* of values with a `:`, e.g. `A1:B2`.

## Autofilling
Enter 1 in `A1`.  Enter 2 in `A2`.  Select `A1` and `A2` with the mouse.  In the
bottom right hand corner of the selection a small handle/plus sign appears.
Drag it down and the spreadsheet will fill in the numbers between 1 and 10.

!!! tip

    Autofilling works with formulas too, in which case references will be
    updated by row if you drag down or by column if you drag across.  If you do
    not want a reference to be updated, prefix it with `$`.  Thus `$A1` will not
    update if dragged across, but will update if dragged down, whilst `A$1` will
    not update if dragged down, but will update if dragged down, and `$A$1` will
    not change in either direction.  
    

!!! note "Exercise" 

    If you find this confusing, the best way is to try. Enter
    `=2*A1` into `B1` opposite your list of numbers and autofill it down.  Then
    select the whole column and autofill it to column `C`.
    
    Now delete column C and enter `=2*$A1` into `B1` and autofill in both
    directions again.
    
## Basic operations

!!! note "Exercise"

    Make a list of numbers between 1 and 20 in column `A`.  In column `B`,
    autofill a list going up in 2s.  In successive columns calculate the

    - multiplication
    - division
    - addition
    - subtraction
    - exponent
    
    of columns `A` and `B`.

!!! note "Exercise"

    Add a column calculating the total of each row (use `+`).
    
!!! note "Exercise"

    Add a single cell adding up all the totals.
