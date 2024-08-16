# markdown-from-file

This is a simple plugin to make it possible to put your markdown in a separate file within [lektor](https://github.com/lektor/lektor).

## Usage

First, change your model so that you are using the `markdown-file` field.

Original `page.ini`:

```
[fields.body]
label = Body
type = markdown
```

Update to look like this:

```
[fields.body]
label = Body
type = markdown-file
file = _contents.md
```

Next, put your Markdown content in a separate file called `_contents.md`. Your `contents.lr` file is likely to be very short and just contain metadata

`contents.lr`:

```
title: An example of markdown in a file
---
body:
```

`_contents.lr`:
```
# Title

This is a Markdown file. Yay!
```

From there, build as normal.
