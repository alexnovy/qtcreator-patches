# qtcreator-patches

I really like QtCreator, but some of its quirks get in the way of my workflow, and I often find myself missing a few features.

Unfortunately, I don't have the time or desire to dig into the QtCreator codebase myself — even though I occasionally look at the Qt source code, which is remarkably clear and well-written. I’m also not interested in submitting official feature requests and arguing for their necessity. It's entirely possible that these features are only useful to me.

Instead, I pulled the latest commit at the time (`a471626826 - Build: Fix Debian packages`) for QtCreator version 20 from GitHub and used Claude to implement a few modifications.

I am sharing these changes as patch files, which you can apply using the following command:

```bash
git apply *.patch
```

### Detachable Output Panes

I frequently need to view "Search Results" and "Application Output" at the same time. While "Application Output" can at least be routed to an external terminal, "Search Results" requires a substantial amount of screen space. During debugging sessions, these auxiliary panels shrink the main code editor so much that it becomes frustrating to work.

`detachable-output-panes.patch` allows any output pane to be turned into a fully functional, independent window and docked back. It adds an "Open in Separate Window" button to the top-right corner of each pane.

### Detachable Sidebars

`detachable-sidebars.patch` allows the sidebars to be popped out into a fully functional separate window and docked back. An "Open in Separate Window" button has been added to the top-right corner. Entering debug mode will no longer automatically hide the right sidebar.

### Fold Markers

I used to completely disable the code folding panel because accidentally clicking anywhere on it would collapse the code.

`fold-marker-click.patch` fixes this by requiring you to precisely click the arrow icon to fold or unfold code.

### Numbered Bookmarks

Back when I used C++Builder, I grew fond of working with numbered bookmarks: `Ctrl+Shift+1..9` to set a bookmark, and `Ctrl+1..9` to jump directly to it. Note that because `Ctrl+1...` shortcuts in QtCreator are normally used to switch workspace modes, but I prefer switching between modes with the mouse anyway.

`numbered-bookmarks.patch` implements this numbered bookmark system.

---

Thanks to these tweaks, I like QtCreator even more now!

If anyone else finds these patches useful, I'll be glad.
