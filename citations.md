# Citations Untangled: the Manual (CUM)

Style Guide for Citations and Explanatory Notes: This is a summary of the suggested practices to take in this repository when it comes to these matters.

## TOC

- [Explanatory notes](#explanatory-notes)
  - [Asides](#asides)
  - [(Actual) explanatory notes](#actual-explanatory-notes)
  - [Endnotes](#endnotes)
  - [Summary and points to note](#summary-and-points-to-note)
- [Citation style](#citation-style)
  - [In-text references](#in-text-references)
  - [Bibliographies](#bibliographies)
  - [Shared bibliography](#shared-bibliography)
- [Miscellaneous notes](#miscellaneous-notes)
- [References](#references)

> **Aside: Motivation**
> 
> The author has seen a variety of academic style guides (APA, Chicago, IEEE to name a few). While they are certainly professionally academic (what ridiculous words to put next to each other) and serve their purpose well, they tend to become somewhat unwieldy for some reasons:
>
> - Across different styles, each bibliographic citation is always a permutation of the same information, albeit in a different presentation.
>   - A DOI identifier should suffice to eliminate metadata beyond author name and reference material title.
>   - Citing webpages is not always easy because webpages may have useless titles (the ones with `<title>` tags), but the actual title is somewhere else in the webpage.
> - Assuming maintaining an up-to-date and correct bibliography at the end of the passage is fine, it is _not_ fine when you have to spend time managing the _in-text_ citations as well.
>   - The author has a personal pet peeve against IEEE citation in particular, because passage-end citation order is the same as the order by which the in-text citations appear. That means if you have to add a paragraph somewhere all your lovely reference numbers will likely need to be shifted.
>   - The other styles may use author names or reference material titles as in-text citation markers. It's fine, but can get long and inconvenient (e.g. gets in the way of the text).
> 
> For our purposes today, those are too formal and annoying to use, but a consistent, convenient and comprehensible citation system is required. Taking inspirations from Wikipedia's style (where footnotes look quite similar to references, which is nice) as well, a simple-ish style guide is devised.

## Explanatory notes

Explanatory notes are segments of text that help to further detail an idea, but the readers are not obliged to read them immediately with the flow of the text (the main body of a text is what's being read). For example, a footnote is a piece of supplementary information that is placed unobtrusively in the middle of a paragraph, which a reader may optionally interrupt his/her reading flow and go check.

This guide describes three kinds of explanatory notes.

### Asides

An aside is used for a large block of text that supplements an idea. An aside always consist of multiple sentences or multiple paragraphs; but they are never so long that they could be a complete document / section (subject to author's discretion) of their own.

In Markdown, asides are like block quotes (`>`), except the first line always starts with `Aside:` (ideally bolded as well).

Asides are placed behind the curiosum to explain as closely as possible, such that if a user opts to read it, the aside would naturally follow and annotate what is being discussed at hand without jumping away too abruptly. Succinct asides (no hard thresholds, maybe within a couple sentences) should be an explanatory note or an endnote, depending on whether it's worthwhile to keep them close to the subject / referent being explained.

An example of asides is the motivation section above, which is something for your interest only, you don't need to read it. But placing it in its own section is more like forcing you to read it (my discretion), and it's too long for an endnote (obviously).

### (Actual) explanatory notes

An (actual) explanatory note is like a footnote that you normally understand: A small marker next to a curiosum, and by following that marker you could find a very short piece of explanatory text supplementing the idea. This piece of text would be found at the end of the printed page (not applicable to us, hence not called "footnotes"), or for our case, closely after the subject / referent.

(Actual [note 1]) explanatory notes consist of two elements: A reference and a dictionary.

References are inserted behind the thing / word / phrase it explains. It is a pair of square brackets enclosing a reference identifier. This identifier consists of a prefix `note-` (or `note `; prefix is customizable) and a short identifier (ideally less than 3 characters). The short identifier should be unique in the immediate surroundings (same paragraph / adjacent few paragraphs / same section, i.e. unique in scope). An example would be `[note 1]`; or use RegEx `r/\[note(-|\s).{1,3}\]`. The identifiers need not appear in the text in ascending alphanumeric order. It is preferable to keep 1 space character between the reference's open bracket and the preceding character.

At the end of the "immediate surroundings", a list would be present as the dictionary. Each list item will be in the format `[$reference_identifier]: $text_description` (colon optional) for bulleted lists, or the list can be a numbered/ordered list, with each row being `[$reference_identifier] $text_description` instead. Sort the dictionary by ascending order of the reference identifiers. It is preferable to precede the dictionary with a line like `Notes:` as a visual cue.

The end of the dictionary marks the end of the scope / validity of the explanatory note reference identifiers. As a result, reference identifiers can be reused in the document without confusion (not necessarily good but you do you).

Explanatory notes like these are like paragraph notes in practice. They are devised and included such that the small nuances that may interest readers are not placed far away (at the end of the document for example), such that the readers need to skip there and come back, risking their attention / reading flow in the process. Thus, explanatory notes are best for explaining subtleties that are useful in the immediate context only.

This section comes with an example for it.

Notes:  
[note 1] I think I would stop saying "(actual)" now that the context _should_ be clear.

### Endnotes

Endnotes are also annotations with an in-text reference identifier and a dictionary to resolve the references. They differ from explanatory notes in two ways:

- The reference identifiers chosen are unique throughout the document, and need not have a prefix.
  - As a corollary, the scope of endnotes is the entire document.
  - The length of the endnote reference identifier can be very short [a], and authors should ensure they look reasonably distinct from explanatory notes.
- The resolving dictionary is to be placed at the end of the document, just before the bibliography (if there is one; see next sections).
  - This ensures the endnotes (and explanatory notes too, really) can contain citations of their own.
  - The dictionary should be preceded by a suitable heading (e.g. `## Notes`), and can be a section under a top-level `# Appendix` section.

They are used to explain details that are least immediately important. An endnote has been included in this section as an example.

### Summary and points to note

The following is a reference "TL;DR" for the 3 kinds of explanatory annotations [nb 1]:

| Type | Length | Immediate importance [nb 2] | Placement |
| :--- | :--- | :--- | :--- |
| Aside | long | medium | adjacent |
| Explanatory note | short | medium | end of section |
| Endnote | short | low | end of document |

Notes:
- [nb 1]: Look, I should have called them this way.
- [nb 2]: As in, how relevant this supplementary info is to the immediate context of the text. If something is really important and relevant, it should have been in the main text by the way.

There may be times when we need to **escape** the square bracket. Either use the explicit escape character `\` (bad) or double the bracket to escape (`[[not a note]]`).

## Citation style

The following sections concern the use of bibliographic citations concept. To be fair, we are *not* strict in maintaining a bibliography. The style will be very much similar to Wikipedia's [1] or IEEE's standard.

Whether to put a citation or a link to a website for further reading is not a trivial matter. While both provide pointers for further investigations, a citation is used to (1) prove you are not plagiarizing and (2) indicate it is less immediately relevant to *do* the further reading. In contrast, inline links and the like provide relevant info, and may not necessarily be cited in the text.

Some citation examples are included in this document.

### In-text references

In-text citations are same as Wikipedia's in-line citations [1], and visually look like IEEE's [2]. They are placed after the thing for which the citation is given.

Physically, each in-text citation is the same as a square-bracketed reference identifier. The identifier should be a short string, preferably a number, unique across the entire document (exceptions are given in the [Shared bibliography section](#shared-bibliography)). The number need not be strictly increasing through the document - you can add references as an afterthought and break the numbering, as long as the number has not been used before it will be fine.

You can have multiple references for one thing - then use commas to separate the identifiers (sorted asc.) in the square brackets.

It is preferable to keep 1 space character between the reference's open bracket and the preceding character.

### Bibliographies

A section dedicated to resolving the in-text references as a dictionary (welp, bibliography) should be added at the end of the document, under a suitable heading (e.g. `## References`). The layout of each entry is the same as explanatory notes; the entries should be sorted in alphabetical order (numbers come before letters by the way).

The difference lies in how the usual citation elements are presented. In general, the formats are as follows:

- Webpages: [[*Author Last Name*, *Initials*]] [[,*Other Author Last name*, *Initials*.]] "*Webpage title [n1]*", *Website name*, retrieved [n2] [[on]] *date* [n3] from *URL*.
  - This is a catch-all category for the time being. Any webpages that are not a download of a file go into this category.
- Online multimedia: *Performer/author last name [n5]*, *Initials* [[,*Other performer/author last name*, *Initials*]]. "*Work title*", [[*Compilation / album name* ([[*year published*]], [[*publisher name*]])]], retrieved [[on]] *date* from *URL*.
  - This is a makeshift setup and different kinds of media might require different formats.
- Online documents in general: [[*Author Last Name*, *Initials*]] [[,*Other Author Last name*, *Initials*.]] *"Document title" [n1]*, [[*Website name*]], [[*Publisher name / information [n4]*]] [[(*DOI link or ID*)]], retrieved [n2] [[on]] *date* [n3] from *URL*.
  - This is another catch-all category for documents and files downloaded online.

Formats for other materials are to be added as required.

> **Aside: About the formats**
> 
> Double square brackets indicate the element is optional.

Notes:  
[n1] Either the title shown on the tab (from HTML `<title>` tags) or the implied title (largest heading that captures the point of the whole thing) are acceptable.  
[n2] This word can be abbreviated, e.g. to `ret.`, or outright omitted (as the date and URL tells you when and where this was found and taken for reference).  
[n3] Use a date in the ISO format.  
[n4] There are no strict rules for this yet, because I doubt anyone will actually care about it.
[n5] If composer, arranger, lyricist and performer are available, then... There aren't any fixed order yet, for indexing I'm not sure what is the best order.

### Shared bibliography

This is strictly speaking not best practice, but there may be reference materials that are reused repeatedly across documents, to the point that you want to extract them to keep the references [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself).

These materials should first be assigned a special reference identifier. Unlike usual citations, a single number should not be used, but a longer piece of text - preferably still concise, of course - such as `Knaff et al. 2016` or `JTWC 35kt radii 2016`. The reference identifier of choice should be unique across the entire body of work. Other than that, in-text citations behave the same way as before.

Then, the resolving dictionary / bibliography for these identifiers will no longer be placed in the same document. A dedicated document (e.g. `bibliography.md` or `references.md`) should be created, hosting the reference resolutions in the usual style.

The references file should be placed in the same folder as the referencing document. To reference the shared material / citation from *another* folder, then the specific entry of the dictionary should be relocated to another reference file (or move the whole thing altogether), located at the folder where all referring documents are its children or indirect children. In other words, to resolve unresolved reference identifiers in a document, search in the current folder (where the document resides), and then move towards the root of the repository - there should be a references file along this path which will resolve the reference.

## Miscellaneous notes

[a] A more traditional style of notating endnotes or footnotes is to use "daggers". If you feel like it, you could use them as well - just place the character inside the square brackets.

## References

- [1] "Wikipedia:Citing sources", Wikipedia, ret. on 2025-04-09 from https://en.wikipedia.org/wiki/Wikipedia:Citing_sources.
- [2] "IEEE Reference Guide", IEEE Publication Operations, ret. on 2025-04-09 from https://journals.ieeeauthorcenter.ieee.org/wp-content/uploads/sites/7/IEEE_Reference_Guide.pdf.
