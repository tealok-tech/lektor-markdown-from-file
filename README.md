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

`_contents.md`:
```
# Title

This is a Markdown file. Yay!
```

From there, build as normal.

## FAQ

### Does it _have_ to be `_contents.md`?

No, you can configure it to anything you awnt in the `page.ini` (or whatever model config file you're using). Just remember that we are relying on the default pattern for the default exclusion pattern for attachments to avoid uploading the Markdown source on deployment.
