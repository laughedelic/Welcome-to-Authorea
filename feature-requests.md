# Feature requests

- Importing repos from Github
- Direct cloning document as a git-repo (no Github involved)
- Editing document sections/chapters separately within common web-interface.  
  I see that one can access to the `Data` of a document and paragraphs/sections are stored as separate Text/Markdown/TeX files there. One can even edit them with some strange separate editor (I suppose it's primarily for _data_). Would be nice to work on the chapters or just some arbitrary parts of the document in the same way as the whole thing is edited curretly and then assemble them in one document (as it is done in `layout.md` currently). Overall idea is to have some correspondence between the document layout and it's table of contents and have some basic interface for manipulating it (i.e. "assembling" the document).
- Web-interface for managing the document structure would be nice, but not essential, from my point of view. Much more important would be a flexible convention upon the structure of the underlying repository: `layout.md`, `title.md`, `bibliography/`, etc.
  + First it would be better to have _special_ files somehow distinguished from the "user-produced", e.g. `_layout.md` or `.layout.md`, same for `title.md` and the assets subfolders
  + Naming paragraph files randomly is not very user-friendly. The whole concept of file-per-paragraph is quite strange, although technically understandable. Looking at Authorea from another side, I would prefer to manage my files/parts of the master-article by myself (and probably store them in some nested folder structure) and then assemble them with some `layout` mechanism (which currently also doesn't look extremely flexible).
  
