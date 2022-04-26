# 2LaneMDr

Build a two-lane README without duplicating your markdown

**Heads up**: this README is available in two forms:
<!-- 2L IF long -->
  a [short and to-the-point](readme.md) one,
<!-- 2L ELIF short -->
  a short and to-the-point one,
<!-- 2L ENDIF -->
and
<!-- 2L IF long -->
  a longer one
<!-- 2L ELIF short -->
  a [longer one](long_readme.md)
<!-- 2L ENDIF -->
with explanations and more details!
_(and, yes, both are auto-generated with 2lanemdr itself, of course)_

### What is this?

Write a single `README.md` with a couple of unobtrusive annotations
and have it automatically spawn two Markdown files.
<!-- 2L IF long -->
Typically,
a "short" one for live workshop and a "long" one for folks who
are not following the live and rely on the README for everything.
<!-- 2L ENDIF -->

<!-- 2L IF long -->
This is the solution I propose to the unavoidable dichotomy between
these two types of workshop consumers:

- I agree that very verbose READMEs make it hard for folks to just locate the commands they are supposed to use as the workshop proceeds;
- but I also see value in a detailed writeup, catering to those who consume the content detached from the live event;
- finally, _I do not think that splitting into sub-chapters or abusing the `summary` feature are the right solution_, so here we are.
<!-- 2L ENDIF -->

Once this is in place, you just edit a "source" README and
pre-commit hooks take care of the rest.

Enjoy!

### Setup

Create an executable `.git/hooks/pre-commit` file with:
```bash
#!/bin/sh

if [ -f ".2lanemdr/2lanemdr.py" ]; then
  ./.2lanemdr/2lanemdr.py
fi
```

That's it.

<!-- 2L IF short -->
For the rest of setup, look at this repo.
<!-- 2L ELIF long -->
Look at the definitions in `.2lane.info` to get the idea.

You can have a look at the (very simple) "annotations"
(i.e. HTML comments on their own line)
in `_src_readme.md`.
They look like


    <!-- 2L IF long -->
    text for long-readme only
    <!-- 2L ENDIF -->
    shared parts
    <!-- 2L IF short -->
    short-readme-version of X
    <!-- 2L ELIF long -->
    long-readme version of X
    <!-- 2L ENDIF -->
    shared part again

<!-- 2L ENDIF -->

### Try it out

Clone the repo, play with the "annotations" in the "source README",
then run `git commit` and check the "result READMEs".

<!-- 2L IF long -->
Try to break the syntax (mismatched IFs, out-of-place ENDIFs, and so on).

The script also tries to catch possible misspelled directives and warn you
(and does a terrible job at that, for now).
<!-- 2L ENDIF -->

<!-- 2L IF long -->
### That's it

That's it. I plan to test this feature with my next workshop,
one where the "scary-wall-of-text-README" got to thunderous proportions:
we'll see.
<!-- 2L ENDIF -->

### Known limitations

I did not feel like writing a full parser, so
if you use a line that looks exactly like `<!-- 2L ENDIF -->`
or similar in a code block, you're currently screwed. Sorry.

<!-- 2L IF short -->
> Congratulations for reading so far "my dear live-workshop attendee".
<!-- 2L ENDIF -->
