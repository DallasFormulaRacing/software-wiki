# Style Guide

As far as styling guidelines go for any official project or resource documentation, there is some flexibility depending on the project, but in almost all cases they should follow closely in line with the guidelines listed below.

## Documentation guidelines

Project documentation is one of the most important aspects of being a developer. As "unfun" as it can be to explain how your project works to an infant, it gives you ample insight into how you can make your project more usable for other developers on our team, while also enabling new members to start working with the code that you have written.

Going into any documentation for DFR, you should have the mindset of needing to explain everything that you can in as much detail as possible. Even if that means explaining some very basic things that might not be valuable to you, this kind of documentation for new members who may know little to nothing about development, let alone CS as a whole, is incredibly useful. Now, this doesn't mean that you need to explain every single line of code that you write, and unlike many of the beginner-level CS and SE courses here at UTD, you will not be required to document specific statements within your code, primarily the highlights, so any functions, class definitions, and overarching project goals, should be explained in as much detail as possible, while also being as **verbose** as possible.

What **"verbose"** means is partially up for interpretation as everyone has their own individual writing styles, however, at its core, being **verbose** means that you describe everything as "simply" as you can. "Simply" in this case not meaning low word count, it instead means in a method that is the easiest to understand. For example, if you were to describe to someone who has no clue what a Python `dictionary` object is by saying it's a "way for you to use custom indexes for data storage under a single variable declaration," they would likely have no clue what that means. Instead, it would be better to describe a Python `dictionary` as "a means of storing multiple data points under one variable declaration, where each data point has its own unique name, known as an index." In essence, don't describe your functions as if the end user knows what they do based on their name alone, ex. for a function you should describe what the function does as a whole initially, then describe each of the required arguments for that function, and what the expected values of those arguments are. It's also generally a good idea to include an example usage of your work, whether that's an entire file, or just a single line snippet included after each documented chunk, it's incredibly useful for someone just learning how to use your work.

## Headings and titles

All section titles should use [Title Case](https://apastyle.apa.org/style-grammar-guidelines/capitalization/title-case). This means that every major word in a sentence should be capitalized in correspondence with the APA standard. 

```md
# This is the Title of a Document
```

[Sentence case](http://grammar.about.com/od/rs/g/Sentence-Case.htm) should be used all for headings. In essence, only capitalize the first word; other words in the sentence are only capitalized if they would normally be in a sentence. (Things like names, places, and so on, just follow general writing guidelines. This does NOT MEAN use punctuation, unless specifically required.).

When making headers, make sure to nest your headings for related topics. For markdown-based documentation, this is done by using increasing numbers of `#` followed by the heading's text. Each "major" section (such as a list of classes, functions, how to use your code, and so on.) should all be defined by a `##` header. Single `#` headers are reserved for titles only, and in order to keep our documentation neat and presentable, any major sections should be documented by the usage of `##`

If you haven't noticed already, the sidebar of our Wiki lists all the important headings in order of how they appear within their respective Markdown files. Each of the subsections that are displayed underneath each major section, such as [New to CS/SE](../onboarding/new-to-CS-or-SE.md), is a result of one of the first three heading identifiers being used, `#`, `##`, or `###`.

**Example header hierarchy**
```md
# This is the Title of a Document

## This is the primary header

### This is a nested header
```

**Example page layout**
```md
# My Project

## Introduction

### Our goal

## Getting started

### Installation

### List of functions

#### Function 1

#### Function 2
```

### Back-to-back headers

When you have a header right below another header, you should include a section break using a [horizontal rule](https://www.markdownguide.org/basic-syntax/#horizontal-rules) (---). As the section below is an example of this, without the inclusion of a triple dash there is no clear split between the headings besides the slight font size change, whereas with a triple dash, there is a much more evident break between the two headings.

This is **ONLY** required if there is **NO** content between the headings, for example; back to back headings, as detailed below.

```md

## Heading 1

---

### Heading 2
```

## Formatting conventions

---

### File names, file paths, variables, literals, and endpoints

All filenames, filepaths, variables, literals, and endpoints, should be enclosed within [backticks](https://www.devx.com/terms/backtick/). In Markdown, this allows you to render anything between the two backticks inline and with fixed-pitch font. This is incredibly useful for anything code-related where readability is imperative. Below is a list of proper usages of each of these requirements.

* File names and directories (file paths); for example `main.py` or `app/main.py`.
* Any code elements when used inline, such as object names, function calls, and so on; for example `variable = None` or `app.main()`.
* URLs and endpoints, unless they are not code critical, such as citing a source or external site for additional information within your docs; for example `http://127.0.0.1:8000` or `home/about`.

### Code samples

Code samples longer than a single line should be put within an appropriate [fenced code block](https://www.markdownguide.org/extended-syntax/#syntax-highlighting) via the usage of 3 backticks (```) or 3 tildes (~~~). Unless there isn't a given language for your sample, you should always specify the language being used in a fenced code block to enable syntax highlighting. Examples of the difference between non-highlighted and highlighted can be found [here](https://www.markdownguide.org/extended-syntax/?#fenced-code-blocks). However, below you can find an example of a properly formatted code block with syntax highlighting for the [Python](https://python.org/) language.

```py
import random

print(random.randint(0,9))
```

### Lists

Use numbered lists only when the order of the items is important; for example, the steps in a procedure: 

1. Step one
2. Step two
3. And so on

Use bulleted lists when you have three or more items in a list in which the order does not matter; for example:

Lists:

* Are easier to read than large blocks of text.
* Make items stand out.
* Clearly identify parallel items.

**NEVER** use a bullet to start a regular paragraph.

**ALWAYS** capitalize items in a list, and end each item with a period **ONLY** when ending a sentence; such as:

* In this example.
* In this other example.
* In this final example.

**NEVER** end a list with a comma, semicolon, or colon.

### Notes, warnings, and related information

Because of the documentation framework we are using, we have the ability to declare specific blocks of related information. This is **NOT** a built in feature of Markdown, and instead is a part of an extension for [MkDocs](https://www.mkdocs.org/) called [Admonitions](https://python-markdown.github.io/extensions/admonition/).

All notes, warnings, and any related information should be placed into their respective admonitions. 

To declare an admonition, start a line with (!!!) followed by the type of admonition you want to use, this can be any of the following types, `note`, `abstract`, `info`, `tip`, `success`, `question`, `warning`, `failure`, `danger`, `bug`, `example`, and `quote`. After you have (!!!) followed by your type, such as `!!! info` you then should specify a name for the block in quotations. Finally, make a new line and indent then type out the content of the admonition.

```md
!!! info "This is an info block"
    Just some info!
```

!!! info "This is an info block"
    Just some info!

```md
!!! warning "This is a warning block"
    Warning!
```

!!! warning "This is a warning block"
    Warning!

```md
!!! failure "This is a failure block"
    Failure!
```

!!! failure "This is a failure block"
    Failure!

## Spelling, grammar, and usage

Use American spelling and grammar: "behavior" instead of "behaviour," "color" instead of "colour," and so on.

Collective nouns, such as organizations, are singular, not plural:

* **CORRECT**: DFR is a club at UT Dallas (standard American usage).
* **INCORRECT**: DFR are a club at UT Dallas (standard British usage).

In lists of three or more items, use the [Oxford comma](https://www.grammarly.com/blog/punctuation-capitalization/what-is-the-oxford-comma/).

Do not use Latin abbreviations, which may not be understood by all readers. Instead, use the English equivalent:

* Instead of "i.e." use "that is."
* Instead of "e.g." use "for example."
* Instead of "etc" use "and so on."

Punctuation should be put **inside** quotation marks when applicable. For example:

```txt
"Hello," "hi," and "greetings" are all proper ways to greet someone.
```

However, there is an exception to the above rule. In the event that you are declaring a literal within quotations, or if the meaning would otherwise be unclear, then you are able to put the comma outside of the quotation mark. For example:

```txt
At the prompt enter "Y", then press Enter on your keyboard.
```