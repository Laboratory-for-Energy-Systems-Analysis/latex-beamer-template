# LaTeX template for PSI slide presentations

## Usage restriction

Only for internal use by PSI employees for scientific presentations that require a lot of mathematics and cannot be done with the offical powerpoint template.


## Description

- The template is provided by a package, which is for use with LaTeX's `beamer` class; the package file name is `PSI43.sty`
- An example input/output is in the files `PSI_test.tex` and `PSI_test.pdf`
- Both common aspect-ratios are supported: 4:3 and 16:9
- This is a lightweight package: 
  - The package does not load other packages apart from the font-related packages from LuaTeX
  - The default beamer theme gets preserved as much as possible: E.g. no proper _inner_ or _outer_ beamer themes are defined


## Usage

You need to select LuaTeX to compile (perhaps XeTeX would also work). LuaTeX is included in standard TeX distributions (e.g. TeX Live or MikTeX). If you use Overleaf, you have to change the compiler [Overleaf Change Compiler](https://www.overleaf.com/learn/how-to/Changing_compiler). Reason: The common pdfTeX engine cannot access the system fonts Calibri and Georgia. For quick drafting: Compile with pdfTeX (without the package), and then with LuaTeX for final design.

1. Place the four files `PSI43.sty`, `PSIlandscape43.jpg`, `PSIlandscape43WirSchaffenWissen.jpg`, and the logo file `PSI.pdf` in your folder of your presentation's .tex file (or somewhere in the LaTeX search path). If you work with 16:9 aspect-ratio, place also the other two pictures: `PSIlandscape169.jpg` and `PSIlandscape169WirSchaffenWissen.jpg`
2. Use `\documentclass[aspectratio=169]{beamer}` in your .tex for 16:9 (`43` should be the default in beamer)
3. Use `\usepackage{PSI43}` in your .tex, see the example file `PSI_test.tex`
4. PSI's _Thanks_-slide is inserted with `\PSItrailer{title}{text}`, where the text is put into a minipage
5. You can use the usual fields of beamer: `author`, `institute`, `title`, `subtitle`, `date` 


## Options

- _Thanks_-slide: The default width of the minipage is `0.4\textwidth`. The width can be given with an option, for example `\PSItrailer[0.6\textwidth]{title}{text}`
- New convenience commands: 
  - `\PSIvspace`; can be placed after the beginning of a frame. It puts a vertical space, such that the content starts vertically at the gray box if a single-line frame title is used and if the beamer frame `t` top-align option is used.
  - The packages defines some rgb colors that can be used: `\PSIgray`, `\PSIlightgray`, `\PSIverylightgray`
- Package options: 
    - `blockcolored` (e.g. `\usepackage[blockcolored]{PSI43}`). If this option is used, the blocks of the beamer class are colored; the default beamer theme has uncolored boxes. See `PSI43.sty` for the colors, which you can change there in place, or you can copy them into your .tex file for changes.
	- `PSIitemize`: use smaller bullets; do not indent itemize lists; use dashes for subitems; do not use smaller font for subitems
- Text size. For smaller text, you should be able to use the usual beamer documentclass options:
  - `smaller` (I think this is 10pt). Things should stay OK.
  - `9pt`. In this case, beamer makes titles smaller, and the package counteracts this. Also, the right margins are smaller by the package, such that you can pack more on the slide. 



## Caveats

- Mac users: The fonts `Calibri` and `Georgia` may be required to be imported into the font managament of MacOS (called `Font Book` or similar)
- LuaTeX expects utf-8 encoded .tex files (in fact, this is now the standard in text processing). Utf-8 allows to use non-ASCII characters directly (e.g. German Umlaute). Related, the LaTeX package `inputenc` should not be used anymore
- Because of LuaTeX, packages `inputenc`, `fontenc`, and `textcomp` should not be loaded
- The package `amsmath` should be loaded before `PSI43` (because the package loads `fontspec`, which should be loaded first)
- The package loads the following packages: `fontspec`, `microtype`
- LuaTeX needs a little bit longer to compile than pdfTeX; especially the first time, when the font maps have to be created. As said, comment-out the package for rough drafting, and run with pdfTeX
