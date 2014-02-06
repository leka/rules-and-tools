# Markdown & Pandoc

## About

This document defines the way Markdown must or should be used.

At Leka, we decided that it would be more convenient to use `.md` for everything we write. The reasons are simple:

*	no need to use Microsoft Word: a simple text editor is enough
*	speed of editing: large files are just text
*	ease of formating: no need to find the Header 1 style in the list, you just write `##`
*	content and form are finally independent
*	you can use your favorite `scm` to track, collaborate and manage all your precious content

Of course `.md` are useless if you want to send your business plan to an investor. That's where [Pandoc](http://johnmacfarlane.net/pandoc/) comes in. We can now easily transform our `.md` files to `.docx` or `.pdf`.

This document gathers documentation found at different places on the Internet.

## Markdown Documentation & Elements

Most of the time we follow the standard [Markdown documentation](https://daringfireball.net/projects/markdown/syntax) by [John Gruber](https://daringfireball.net/).

We will only document our specific aspects. Those aspects are compatible with a `.docx` or `.pdf` export.

**IMPORTANT:** Beware if you try to use exotic features like tables, we haven't tried them out yet. Stay tuned for improvement in the future.

### Headers

Here we will show different type of headers from `0` to `4`. Number `0` is the title of the document and therefore **should not** be used more than **once**.

*	# --> Title of the document
*	## --> Header 1
*	### --> Header 2
*	#### --> Header 3
*	##### --> Header 4

### Paragraph

Paragraphs follow the standard [paragraph documentation](https://daringfireball.net/projects/markdown/syntax#p).

### Lists

Lists follow the standard [list documentation](https://daringfireball.net/projects/markdown/syntax#list).

### Emphasis

Emphasis follow the standard [emphasis documentation](https://daringfireball.net/projects/markdown/syntax#em).

### Images

Images can be included inside a `.docx` document. Images follow the standard [image documentation](https://daringfireball.net/projects/markdown/syntax#img).

You must make sure your images have the right size so you won't have to resize them all in Word. We also recommend putting your images in an `img` folder inside your `project` folder.

This repo is a good exemple:

```
.
|-- README.md
|-- example.md
`-- img
    |-- Logo_Leka_Small.png
	    `-- Logo_Moti_Sphere_Large-02.png
```

By doing so, you can reference your images this way:

```
![My Super Logo](./img/Logo_Leka_Small.png)
```

### Footnotes

When writing a report, a business plan or anything else, it's always convenient to put your sources as footnotes.

The raw version of Mardown doesn't really support footnotes but Pandoc does provide a way to write footnotes for `.md` and export them as real `.docx` footnotes for Word.

Here is an exemple from the Pandoc documentation:

``` Markdown
Here is a footnote reference,[^1] and another.[^longnote]

[^1]: Here is the footnote.

[^longnote]: Here's one with multiple blocks.

	Subsequent paragraphs are indented to show that they belong to the previous footnote.

		{ some.code }

	The whole paragraph can be indented, or just the first line.  In this way, multi-paragraph footnotes work like multi-paragraph list items.
This paragraph won't be part of the note, because it isn't indented.
```

## Pandoc documentation

From the [Pandoc documentation](https://github.com/jgm/pandoc):

> Pandoc is a [Haskell](http://www.haskell.org/haskellwiki/Haskell) library for converting from one markup format to another, and a command-line tool that uses this library.
