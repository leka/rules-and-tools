# Markdown & Pandoc

## Philosophy

At Leka, we decided that it would be more convenient to use `.md` for everything we write. Our reasons are simple:

*	no need to use Microsoft Word: a simple text editor is enough *most of the time*
*	speed of editing: large files are just text
*	ease of formating: no need to find the Header 1 style in the list, you just write `# Header 1`
*	content and form are finally independent
*	you can use your favorite `scm` to track, collaborate and manage all your precious documents

Markdown is designed to be easy to write, and, even more importantly, easy to read:

> A Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions. –[John Gruber](http://daringfireball.net/projects/markdown/syntax#philosophy)

Of course `.md` are useless if you want to send your business plan to an investor. That's where [Pandoc](http://johnmacfarlane.net/pandoc/) comes in and let us easily transform our `.md` files to `.docx` or `.pdf` files.

## Markdown

The version of markdown that we use,[Markdown Extended](http://johnmacfarlane.net/pandoc/README.html#pandocs-markdown) by [Pandoc](http://johnmacfarlane.net/pandoc/), is a revision of the [standard markdown](https://daringfireball.net/projects/markdown/syntax) by [John Gruber](https://daringfireball.net/).

The [Pandoc website](http://johnmacfarlane.net/pandoc/) has an incredibly rich documentation about this [Pandoc Flavored Markdown](http://johnmacfarlane.net/pandoc/README.html#pandocs-markdown).

We really recommend you to read this documentation because it might be very useful for your personal project as well.

We will only document our specific aspects and how we use them. We'll be brief and link to the official documentation for further information.

**IMPORTANT:** Beware if you try to use exotic features like tables, we haven't tried them out yet. Stay tuned for improvements in the future.

## Pandoc documentation

### About

From the [Pandoc documentation](https://github.com/jgm/pandoc):

> Pandoc is a [Haskell](http://www.haskell.org/haskellwiki/Haskell) library for converting from one markup format to another, and a command-line tool that uses this library.

### How to install

To install Pandoc, you can the installer for your operating system or you can build it from source.

The easiest way is to use the installer that you can download from the [installation page](http://johnmacfarlane.net/pandoc/installing.html).

On Mac OS X, if you want to install it from source, you can do as follow:

```Shell
$ brew install haskell-platform
$ cabal update
$ cabal install --force pandoc pandoc-citeproc
```

### How to convert

#### From `.md` to `.docx`

It's pretty simple:

```Shell
$ pandoc -sS MyMarkdownFile.md -o MyDocxFile.docx
```

And if you have plenty of `.md` files in the right order that you want to compile together, you can type the following:

```Shell
$ pandoc -sS *.md -o MyDocxFile.docx
```
#### From `.md` to `.pdf`

It's pretty simple:

```Shell
$ pandoc -sS MyMarkdownFile.md -o MyDocxFile.pdf
```

And if you have plenty of `.md` files in the right order that you want to compile together, you can type the following:

```Shell
$ pandoc -sS *.md -o MyDocxFile.pdf
```

## General features

Here after are all the features that we use as is, out of the box, with no specific rules.

*	[Paragraphs](http://johnmacfarlane.net/pandoc/README.html#paragraphs)
*	[Lists](http://johnmacfarlane.net/pandoc/README.html#lists)
*	[Inline formatting](http://johnmacfarlane.net/pandoc/README.html#inline-formatting)
*	[Verbatim (code) blocks](http://johnmacfarlane.net/pandoc/README.html#verbatim-code-blocks)

## Specific features

Here after are all the features we use in a certain way and that are important to keep consistency in all our documents.

### Headers

We use headers from `1` to `5`.

*	`#`			--> Header 1
*	`##`		--> Header 2
*	`###`		--> Header 3
*	`####`		--> Header 4
*	`#####`		--> Header 5

Link to Pandoc documentation: [Headers](http://johnmacfarlane.net/pandoc/README.html#headers)

### Images

Images can be included inside a `.docx` document.

You must make sure your images have the right size so you won't have to resize them all in Word. We also recommend putting your images in an `img` folder inside your `project` folder.

This repo is a good exemple:

```Shell
MyDirectory
|-- Part-1-Introduction.md
|-- Part-2-Team.md
|-- Part-3-Product.md
`-- img
    |-- MyImage-1.png
    |-- MyImage-2.png
    `-- MyImage-3.png
```

By doing so, you can reference your images this way:

```Markdown
Some paragraph...

![My Super Logo](./img/Logo_Leka_Small.png)

Some other paragraph...
```

Link to Pandoc documentation: [Images](http://johnmacfarlane.net/pandoc/README.html#images)

### Footnotes

When writing a report, a business plan or anything else, it's always convenient to put your sources as footnotes.

The raw version of markdown doesn't support footnotes but Pandoc does provide a way to write footnotes for `.md` and export them as real `.docx` footnotes for Word.

Here is an exemple from the Pandoc documentation:

```Markdown
Here is a footnote reference,[^1] and another.[^longnote]

[^1]: Here is the footnote.

[^longnote]: Here's one with multiple blocks.

	Subsequent paragraphs are indented to show that they belong to the previous footnote.

		{ some.code }

	The whole paragraph can be indented, or just the first line.  In this way, multi-paragraph footnotes work like multi-paragraph list items.

This paragraph won't be part of the note, because it isn't indented.
```

Link to Pandoc documentation: [Footnotes](http://johnmacfarlane.net/pandoc/README.html#footnotes)

## Conclusion

And that's all folks! :)
