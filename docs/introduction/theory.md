# Two ways of working

Let's start with two pictures.  Firstly, we have an accountant in Dickens' time.
He sits stooped over a desk, on the low-ceilinged second floor of a building
which is one floor shop, one floor offices, two floors lodgings and the attic
for the servants.  He has at his right ink-pot and pen, before him, a ledger
book, to his left, older ledger books, rescripts (for so once we spelt receipt),
bills, notes, et cetera.  He writes down figures now above, now below the line
and adds them up in his head with the aid of notes on a scrap of paper.

In this case, *the medium is merely a record*: the work is done in his head.

Secondly, we have a modern accountant using some financial package.  He sits
before a computer in some comfortable (but hideous) 'working space' (for so now
do we spell 'office').  He imports 'data' from emails, using an import wizard,
and the totals appear automagically on the view he selects from the software.

In this case, *the medium is merely a record*: but the work is done by the
computer.

Whilst it is possible to use spreadsheets in this way, there are good reasons
not to.  In the first case:

- A computer offers little advantage over pen and paper when used like this.
- Nobody expects you to do this (though a surprising number do) so you will
  catch people out.
  
In the second case:

- Spreadsheet code (macros, over the top formulae, hidden regions with
  intermediate values) is rarely actively maintained and almost never rigorously
  tested.  It's *bad* code.  Dedicated packages are *much* less likely to have
  bugs in them.
- Spreadsheets are ugly layout engines.
- Spreadsheets, when hacked to look good displaying lots of data, are impossible
  to edit.
  
The ideal medium is somewhere in the middle.  When you write code, the
intermediate values exist somewhere in ram, and you don't know what they are.
(Unless you print them, but you usually only do that in debugging.)  If you want
to make sure your code works, you write unit and functional tests which supply
known inputs and look for the right output---in other words, they treat your
code like a black box.  Testing like this is impossible in most spreadsheet
packages (and makes little sense anyway).  Rather, in a spreadsheet, you have a
kind of magical ledger book which calculates for you.  Note that it does *not*
think for you.  You have to do all the thinking.  If you want a column which
represents the column before squared, it will make one without blinking.  If you
enter the wrong formula, it will double the column.  *You* have to notice that
your square numbers are improperly distributed: the package will not help you.

From this we get our first principle of spreadsheet design:

!!! note "Principle"
    No sheet should be too big or too complicated for an ordinary person, at their
    most tired, to get their head around.  That means:

    - All important columns should fit on the screen
    - No active rows should be hidden under rows of data
    - No calculation should go too quickly.  If you need to do *lots* of things
    to data, use intermediate columns (you can always hide them).
    - Header rows should be fixed if possible.
    - Sheets should be intelligently named
    
There is a corollary of this principle, which is not going to come up in this
tutorial, but which is worth thinking about:

!!! note "Principle"
    When you need to handle more data than you can whilst following the first
    principle, you need something other than a spreadsheet.  You might need:
    
    - A database
    - A financial package
    - Custom software
    - A script
    
    Any of these can handle data which started out in a spreadsheet very easily.

