# Questions

I generally see Authorea as a medium for collaborative writing. I know that there's much more with publishing, but for it's still a bit far away to be concerned about.

Personally, I prefer to use a local setup with my customized editor, Pandoc for generating output, Git with meaningful commit messages, etc. And I want to use Authorea as an interface to be used by other coauthors (my supervisors or colleagues) that don't want or don't need to use git/command line directly: for reviewing, **commenting**, minor fixes and additions that can be easily done through the web-editor _"in-place"_.

So it's important for me to understand how I can write locally, but in a way that won't break the appearance of the article on the web-side exposed to other coauthors.


## Folders structure and special files

What I haven't found in the [docs](https://www.authorea.com/users/77723) is the way Authorea manages the git repo and processes the special files:

- What is the general structure of the underlying git repo, what parts are mandatory and what optional?
- Which special files are there in general and which formats do they use? Here are the ones I found out so far:
  + `layout.md`: the master-document structure, plain list of references to other files (`.md`, `.tex`, also `.html`?)
  + `title.md`: contains the document title string
  + `abstract.md`: just the abstract text
  + `authors.tex`: appears when you try to modify the authors list through the web-interface. Can it be also `authors.md`? Anything else? (see my Pandoc YAML header feature request)
  + `header.tex`: TeX preamble ([related doc](https://www.authorea.com/users/5713/articles/28015)). Not clear how it is incorporated in the rest of the template used by Pandoc internally.
  + `bibliography/biblio.bib`: BibTeX bibliography. Does the name matter? Why the folder? Can I have several files there?
  + `figures/`: folder for pictures. I'm not sure about the structure and format.


## Pandoc and the build process

- Is there a way to pass any options to Pandoc?
- Which Pandoc extensions are turned on by default?
- Is there a way to use XeTeX engine for being able to use Unicode everywhere?
- Is there any way to setup a custom build script for generating the document? I expect no in general, because it would be a security vulnerability, but probably some kind of [TavisCI-like config](https://docs.travis-ci.com/user/customizing-the-build) is used internally and could be exposed to the user.

Update: it appears that there are various solutions to what I described above (wrappers for Pandoc with YAML config to handle any Pandoc options and pre/post-processing):
- [panzer](https://github.com/msprev/panzer#panzer) (python) looks most developed and mature
- [pandocomatic](https://github.com/htdebeer/pandocomatic) (ruby)
- [pdc](https://github.com/bk/pdc) (perl)


## Diagrams

My field is algebra, so I need to draw a lot of [commutative diagrams](https://en.wikipedia.org/wiki/Commutative_diagram) and [string diagrams](https://en.wikipedia.org/wiki/String_diagram). So far I was using the [XY-pic](http://xy-pic.sourceforge.net) TeX package. It's probably not the most modern thing, but it works quite well. I didn't see it on the [list of supported packages](https://www.authorea.com/users/77723/articles/111127/_show_article), so I'm not sure I can use it. I saw the TikZ package on the list though, probably it's a better choice in general, but I'm still not sure that the diagrams will be rendered in the web-interface.

I was thinking that probably a generally better way to work with it is to have diagrams LaTeX/xy-pic code separate and generate SVGs for each of them, then just insert the pictures in the main document. But then I can generate those pictures only locally, no way to change a diagram through the web-interface (thus the question about the build-script).
