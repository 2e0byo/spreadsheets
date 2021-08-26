## Display vs. Content

We said earlier that a spreadsheet was a bit like a computer program which
showed you how it was working.  By this we meant that the intermediate values
are all on show.  However, there is a problem with this idea.  Consider this:

- A bottle of water costs £0.611 when bought in units of 100
- If you enter `£0.611` into `A1` in most spreadsheet packages and press
  enter, you will see `£0.61`
- If you enter `=100 * A1` into `B1` you will see `£61.10`, not `£61.00`

What has happened is that the spreadsheet package has simplified the *display*
of the price of a bottle, without simplifying the value.  But it hasn't stored
'£0.611' as the value of `A1`.  Rather it has stored the number '0.611' and the
information 'this cell is currency'.  Then, because the cell is currency, it has
applied the *currency* format to the *display* of the number (but kept the real
value intact).

Whilst modern spreadsheet packages will guess formatting for you, they sometimes
get it wrong (for instance interpreting `6/7` as a date).  You can apply
formatting manually by selecting a cell (or range of cells) and right-clicking
or going to the *format* menu (depending on the package).

!!! Note

    Sometimes you want to change the actual *value* (for instance, you
    might be calculating a final amount, where you can't pay fractions of a penny).
    In that case you likely want the function `Round` or `Ceiling`.
    
Formatting can do lots of things:

- Add a currency symbol
- Hide decimal places
- Display dates as words
- Apply a colour

The precise functionality depends on the spreadsheet package.

## Conditional Formatting

You can also apply formatting only if the value of a cell meets some condition.
For instance, you can colour negative numbers red and positive numbers green.
The precise means of doing this depends on the package.

Conditional Formatting is an *extremely* valuable tool for allowing *you* to see
at a glance what is happening.  You should consider it every time you are
tempted to colour data, or every time you write a formula with a condition in it
(like `Countif`).

!!! Example

    Imagine you meant to make a count of all cells over 55 in a given range, but
    you entered the condition as `<55` by mistake.  If you also apply a
    conditional format with the same condition, you will see at a glance what
    you have done.
    
    Note that this won't save you from typos!  But it will make it more obvious
    that the number of red cells is not 6, but much more like 50.
    
    It follows that you need to think about testing what you write as you go along.


## Freezing Rows and Columns

Most spreadsheet packages let you 'freeze' a number of rows or columns so that
they stay in the same place as you scroll.  This is a very good idea for header
rows, so that as you scroll off the screen you don't forget what the columns
are.  Just because it fits on your screen doesn't mean it will on everyone's!

## Protecting Cells

Most packages also let you 'lock' or 'protect' cells to forbid editing them.
Think hard about doing this.  It might seem a good idea to you to prevent e.g.
random accidental edits of the VAT value.  But if a colleague can't see how to
edit a protected value, they will likely just circumvent it by editing the
formula directly.  This will leave the sheet in a much worse state, since now
the VAT cell doesn't do anything (or, worse, *two* different VAT values are used.)

## Defining Print Ranges

The process of producing paper reports to hand to clients is beyond the scope of
this tutorial.  But one thing worth knowing is that you can (try to) establish
what goes on which page by defining *print ranges*.  This lets you exclude
things not worth printing, and (usually) define page breaks.

## Overformatting

Remember that people have to *read* your sheet.  Some people have colour
blindness.  Others have glary screens.  Others have small devices.  Others need
to zoom right in.  Keep your formatting clean and minimalist, and avoid
colouring everything with full 80s glory 8-bit colouring.  Avoid the use of
custom or obscure fonts.
