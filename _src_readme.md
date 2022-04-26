# 2LaneMDr

Build a two-lane README without duplicating your markdown

**Heads up**: this README is available in two forms:
a short and to-the-point one,
and a longer one with explanations and more details!
_(and, yes, both are auto-generated with 2lanemdr itself, of course)_

### What is this?

Write a single `README.md` with a couple unobtrusive annotations
and have it automatically spawn two Markdown files. Typically,
a "short" one for live workshop and a "long" one for folks who
are not following the live and rely on the README for everything.

This is the solution I propose to the unavoidable dichotomy between
these two types of workshop consumers:

- I agree that very verbose READMEs make it hard for folks to just locate the commands they are supposed to use as the workshop proceeds;
- but I also see value in a detailed writeup, catering to those who consume the content detached from the live event;
- finally, _I do not think that splitting into sub-chapters or abusing the `summary` feature are the right solution_, so here we are.

Once this is in place, you just edit a "source" README and
pre-commit hooks take care of the rest.

Enjoy!

### Setup

Look at the definitions in `.2lane.info`
and check that the **pre-commit hook** in `.git/hooks/pre-commit` has been
enabled and edited to invoke the 2lanemdr script
(`.2lanemdr/2lanemdr.py`, no need to study it anyway).

You can have a look at the (very simple) "annotations"
(i.e. HTML comments on their own line)
in `_src_readme.md`.

### Try it out

Clone the repo, play with the "annotations" in the "source README",
then run `git commit` and check the "result READMEs".

Try to break the syntax (mismatched IFs, out-of-place ENDIFs, and so on).

The script also tries to catch possible misspelled directives and warn you
(and does a terrible job at that, for now).

### That's it

That's it. I plan to test this feature with my next workshop,
one where the "scary-wall-of-text-README" got to thunderous proportions:
we'll see.
