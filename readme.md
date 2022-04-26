# 2LaneMDr

Build a two-lane README without duplicating your markdown

**Heads up**: this README is available in two forms:
  a short and to-the-point one,
and
  a [longer one](long_readme.md)
with explanations and more details!
_(and, yes, both are auto-generated with 2lanemdr itself, of course)_

### What is this?

Write a single `README.md` with a couple of unobtrusive annotations
and have it automatically spawn two Markdown files.


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

For the rest of setup, look at this repo.

### Try it out

Clone the repo, play with the "annotations" in the "source README",
then run `git commit` and check the "result READMEs".



### Known limitations

I did not feel like writing a full parser, so
if you use a line that looks exactly like `<!-- 2L ENDIF -->`
or similar in a code block, you're currently screwed. Sorry.

> Congratulations for reading so far "my dear live-workshop attendee".
