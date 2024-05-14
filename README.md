[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/R6R4DBTWO)

**2024-05-14**

- [Discussion on Hacker News!](https://news.ycombinator.com/item?id=40342008)
- Welcoming typo corrections and other errata at the [markdown repo](https://github.com/zenodotus280/apl-md).

---

## Preamble
This project is an abridged, hyper-textual, and copyleft manifestation of the 1977 architecture classic *A Pattern Language* by Christopher Alexander. It is compiled from markdown into a static website using [Quartz](https://quartz.jzhao.xyz/). I created it to serve as both an accessible reference for myself and as a way to share the ideas with others.

From the inside cover:

>You can use this book to design a house for yourself with your family; you can use it to work with your neighbors to improve your town and neighborhood; you can use it to design an office, or a workshop, or a public building. And you can use it to guide you in the actual process of construction.

---

> [!cite] Volume 1, *The Timeless Way of Building*
> ... lays the foundation of the series. It presents a new theory of architecture, building, and planning which forms the basis for a new traditional post-industrial architecture, created by the people ...

> [!cite] Volume 2, *A Pattern Language*
> ... is a working document for such an architecture. It is an archetypal language which allows lay persons to design for themselves.

> [!cite] Volume 3, *The Oregon Experiment*
> ... shows how this theory may be implemented, describing a new planning process for the University of Oregon.

---

## This Project in Context
I first read *A Timeless Way of Building* and subsequently *A Pattern Language* some 10-15 years ago and it has forever influenced how I see the built environment and my capacity to appreciate why a room, street, or city feels *right* or *wrong*. Christopher Alexander writes elsewhere about the philosophy and psychology of this in his other books and is best formulated in the "Nature of Order" series.

### Previous Efforts
This is not the first attempt to digitize Volume 2. In the order in which I discovered them:

> [!example]- [Jacana](https://web.archive.org/web/20030618055012/http://www.jacana.org.uk/pattern/P0.htm) (fl. 2003-2019)
>  Discovered soon after I read the books and ultimately inspired me to create my own version. It worked well but it lacked detail and was not easily duplicated as it relied on server-side scripting.

> [!example]- [Nick Trombley (Barnsworth Burning)](https://patternsof.design)
> Created a very clean single-page version but ultimately didn't satisfy my requirements and motivated me to start my own.

> [!example]- The [Official Version](https://www.patternlanguage.com/apl/twopanelnlb.htm)
> Accessible for a $5 monthly donation. The entirety of the book has been digitized but the OCR is not perfect and there are several errors on each pattern including the links to other patterns. The full-text was useful to cut down my transcription time for the *Related Patterns*.

> [!example]- [Theo Armour](https://github.com/patterns-dev) (fl. 2012-present)
> Found recently before I decided to finish my own project. Similar to the official one but with more automation; errors retained.

All of these versions have the following limitations:
- only includes the Problem and Solution text
- no backlinks; existing resources only provide forward links:
	- Official and Nick - inline hyperlink
	- Jacana - "higher/lower order"
	- Theo (New Patterns) - "up/horizontal/down"
- no graph view or grouping via tags for better visualization
	- by 'confidence' (eg. 0,1,2 stars)
	- by 'sub-category' (eg. Liminal Space)
	- by master category (eg. Construction)

## How to Use and Interpret the Patterns
Ideally, you'd read both Volume 1 and Volume 2 in their entirety and then use this site as a quick reference (I created it for myself first and foremost!). But that's not going to happen so here is a very rough summary...

Alexander's approach emphasizes the importance of context-sensitive design and the creation of environments that are conducive to human well-being. He advocates for a participatory design process that engages the users and stakeholders in shaping their towns, neighborhoods, and homes.

> [!tldr]- **The Patterns**
> "Each pattern describes a problem which occurs over and over again in our environment, and then describes the core of the solution to that problem, in such a way that you can use the solution a million times over, without ever doing it the same way." - p. x

> [!tldr]- **The Connection Between the Patterns**
> - ordered in spatial scale: from towns [[Independent Regions (1)]] to the photos on your wall [[Things From Your Life (253)]]
> - each pattern helps to complete the patterns connected to it; no pattern is an isolated entity; all are part of a larger 'whole'
> - reading "up and "down" through the patterns will give you a sense of which ones are needed for your project

> [!tldr]- **Confidence**
> The confidence tags reflects the author's belief that the solution is "correct".
> - High confidence means that "the solution stated summarizes a *property* common to *all possible ways* of solving the stated problem."
> - Medium confidence means that some progress has been made but improvements should be sought through experimentation.
> - Low confidence means that there are definitely other ways of solving the problem that aren't written and that at least a single solution is described as a starting point.

## How It's Made

I'd like to say that I wrote some clever site scraper and then algorithmically generated everything but the real answer is that it was mostly done by hand with a template for the pattern structure, the help of Obsidian's auto-complete combined with a keyboard macro to convert (and correct) the links, and *many dozens of hours* typing, copy-pasting, and tweaking. I reference these patterns directly in my Obsidian vault. I began in 2020 but I didn't work on it in earnest until November of 2023 with a final push in April of 2024.

The "master" version is my Obsidian vault. I have a custom Fish function (`apl-copy`) using `rsync` to copy from my vault to the Markdown repo that contains the patterns (and list of patterns), the README, and the LICENSE as markdown files.

I have another custom Fish shell function (`apl-preview`) to copy the patterns to the 'content' directory in the Quartz repo then build and serve the website locally. A third function (`apl-deploy`) pushes the changes so that GitHub Actions can take over from there. These custom functions save me from the hassle of remembering which commands to use and in which directory.

## TODO
> [!todo]
> - [ ] update each pattern with hierarchical tags for master categories and sub-categories (only three as an example)
>	- [[Independent Regions (1)]]
>	- [[Building Complex (95)]]
>	- [[Structure Follows Social Spaces (205)]]
> - [ ] Utilize aliases in the *Related Patterns* section so that the patterns read more naturally (as in the original) rather than sticking with the canonical pattern name
> - [ ] more consistent use use of dashes, ellipses, and other minor formatting/style choices