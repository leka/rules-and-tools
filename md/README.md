# Markdown & Pandoc

## Philosophy

At Leka, we decided that it would be more convenient to use `.md` for everything we write. Our reasons are simple:

*	no need to use Microsoft Word: a simple text editor is enough
*	speed of editing: large files are just text
*	ease of formating: no need to find the Header 1 style in the list, you just write `##`
*	content and form are finally independent
*	you can use your favorite `scm` to track, collaborate and manage all your precious content

Markdown is designed to be easy to write, and, even more importantly, easy to read:

> A Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions. –[John Gruber](http://daringfireball.net/projects/markdown/syntax#philosophy)

Of course `.md` are useless if you want to send your business plan to an investor. That's where [Pandoc](http://johnmacfarlane.net/pandoc/) comes in and let us easily transform our `.md` files to `.docx` or `.pdf` files.

## Markdown

The version of markdown that we  use is a revision of the [standard markdown](https://daringfireball.net/projects/markdown/syntax) by [John Gruber](https://daringfireball.net/).

The [Pandoc website](http://johnmacfarlane.net/pandoc/) has an incredibly rich documentation about this [Pandoc Flavored Markdown](http://johnmacfarlane.net/pandoc/README.html#pandocs-markdown).

We really recommend you to read this documentation because it might be very useful for your personal project as well.

We will only document our specific aspects and how we use them.

**IMPORTANT:** Beware if you try to use exotic features like tables, we haven't tried them out yet. Stay tuned for improvements in the future.

### Headers

We use headers from `0` to `5`. Number `0` is the title of the document and therefore **should not** be used more than **once**.

*	#		--> Title of the document
*	##		--> Header 1
*	###		--> Header 2
*	####	--> Header 3
*	#####	--> Header 4
*	######	--> Header 5

Link to Pandoc documentation: [Headers](http://johnmacfarlane.net/pandoc/README.html#headers)

### Paragraphs

Link to Pandoc documentation: [Paragraphs](http://johnmacfarlane.net/pandoc/README.html#paragraphs)

### Lists

Link to Pandoc documentation: [Lists](http://johnmacfarlane.net/pandoc/README.html#lists)

### Inline formatting

Link to Pandoc documentation: [Inline formatting](http://johnmacfarlane.net/pandoc/README.html#inline-formatting)

### Images

Images can be included inside a `.docx` document.

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

Link to Pandoc documentation: [Images](http://johnmacfarlane.net/pandoc/README.html#images)

### Footnotes

When writing a report, a business plan or anything else, it's always convenient to put your sources as footnotes.

The raw version of markdown doesn't support footnotes but Pandoc does provide a way to write footnotes for `.md` and export them as real `.docx` footnotes for Word.

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

Link to Pandoc documentation: [Footnotes](http://johnmacfarlane.net/pandoc/README.html#footnotes)

## Pandoc documentation

### About

From the [Pandoc documentation](https://github.com/jgm/pandoc):

> Pandoc is a [Haskell](http://www.haskell.org/haskellwiki/Haskell) library for converting from one markup format to another, and a command-line tool that uses this library.

### How to install

