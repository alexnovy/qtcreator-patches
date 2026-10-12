# qtcreator-patches

I like QtCreator, but some of its quirks are inconvenient for my workflow, and I find myself missing a few features.

Unfortunately, I don't have the time or desire to dig into the QtCreator codebase, even though I occasionally look at the Qt source code—which is written quite clearly. I am also not ready to submit feature requests and argue for their necessity; it's entirely possible that these features are only useful to me.

Therefore, I took the latest commit at the time ("a471626826 - Build: Fix Debian packages") for the 20th version of QtCreator from https://github.com and asked Claude to add a few modifications.

I am sharing only the changes in the form of patches, which can be applied using the command:

```bash
git apply *.patch
```


### Detachable output panes

I quite often need to see the contents of "Search Results" and "Application Output" simultaneously. While "Application Output" can at least be routed to a terminal, "Search Results" requires a significant amount of screen space. During debugging, these auxiliary panels shrink the code pane so much that working becomes uncomfortable.

`detachable-output-panes.patch` allows any Output element to be turned into a fully functional separate window — an "Open in Separate Window" button has been added to the top right corner.


### Fold marker

I used to completely disable the folding markers panel because accidentally clicking on it would hide the code.

`fold-marker-click.patch` forces you to aim precisely at the arrow.


### Numbered bookmarks

In C++Builder, it was very convenient to work with numbered bookmarks: `Ctrl+Shift+1..9` to set a bookmark, and `Ctrl+1..9` to jump to it. Note that `Ctrl+1...` shortcuts in QtCreator are normally used to switch modes, but I prefer switching them with the mouse anyway.

`numbered-bookmarks.patch` adds these numbered bookmarks.

---

As a result, I like QtCreator even more now!

If anyone finds these patches useful, I'll be glad.
