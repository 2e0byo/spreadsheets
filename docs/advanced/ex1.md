## Functions

How do we generate random data?  Most spreadsheets have a function `rand()`
which returns a random floating-point number between 0 and 1.  Most also have a
`randbetween(bottom, top)` function which returns a random *integer* between
`bottom` and `top` (inclusive).

!!! Example "Exercise"

    Generate some random data between 0 and 1 in column A.  Generate some random
    data between 10 and 50 in column B.  Multiply them in column C.  Apply
    formatting to Column B to make it currency.  Does the data change?
    
    Enter something into a cell in column D.  What happens to the random data?
    If nothing happened, enter `=2*4` into the cell and then press enter.
    
    Press F9.  What happens to your random data?  (This may not work in all packages.)
    
So, how do you 'freeze' your random data?  One option is to turn off auto
updating calculations, but that's a *bad* idea as it affects *every*
calculation, not just the calls to `rand()` or `randbetween()`.  Rather, when
you have the data you want, select it and copy it to a new region using *paste
special* to get the *contents* and not the formula.  How this is done will
depend on the package you are using.

## Generate Groceries!

Alright, so I shouldn't have told you to use the same groceries each week.
That's very unlikely, isn't it.

Generate weekly grocery amounts for the last 3 years (you can consider them as
being paid every 7 days) between £50.00 and £250.00.  Make sure the pence change
as well!

When you have your data, copy *just the data* to a new sheet or spreadsheet so
you can use it later.
