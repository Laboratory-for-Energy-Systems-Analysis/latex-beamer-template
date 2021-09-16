# PSI LaTeX template for slide presentations

## Description

- Uses LaTeX's `beamer` class
- An example output is in the file `PSI_test.pdf`; it is not (yet) perfect
- Currently supported format is the 4:3 aspect ratio (and not 16:9)
- I am aware that some time ago somebody else from PSI made also a template. The difference is that we use a lightweight package: It does not load other packages apart from the "fontspec" package from LuaTeX, which is needed because of the fonts. Moreover, there is no proper _inner_, _outer_ theme defined etc. It is just the default beamer theme

## Usage

You need to select LuaTeX to compile to a pdf file (perhaps XeTeX would also work). LuaTeX is included in the standard TeX distributions (e.g. TeX Live).If you use Overleaf, you have to change the compiler [Overleaf Change Compiler](https://www.overleaf.com/learn/how-to/Changing_compiler). Reason: The common pdfTeX engine cannot access the system fonts Calibri and Georgia.

1. Place the three files PSI43.sty, PSIlandscape.jpg, PSI.pdf in your folder of your presentation .tex file (or somewhere in a path where LaTeX searches for files)
2. Use `\documentclass[aspectratio=43]{beamer}`  in your .tex, in fact `43` should be the default
3. Use `\usepackage{PSI43}` in your .tex, see the example file `PSI_test.tex`
4. The _Thanks_-slide is inserted with `\PSItrailer{some text}`, where the text is put into a box
5. You can use the usual fields of beamer: `author`, `institute`, `title`, `subtitle`, `date` 


## Options

- On the _Thanks_-slide, the default width of the box is `0.4\textwidth`. The width can also be given with an option, for example `\PSItrailer[0.6\textwidth]{some text}`
- New convenience command: `\PSIfill`. The beamer class tends to place content in the middle of a slide. Hence, to push content up, put `\PSIfill` below the content, and to push down, put it above. 
- You can use `\PSIvspace` after the beginning of a frame. It puts a vertical space after a single-line title, such that the content starts vertically at the gray box. This works in case the slide is full with content; otherwise, you have to use `\PSIfill` below the content to push up.
- You can use the package with an option: `\usepackage[blockcolored]{PSI43}`. In this case the blocks of the beamer class are colored; this is because the default beamer theme has uncolored boxes. See `PSI43.sty` for the colors, which you can change there in place, or you can copy them into your .tex file for changes.
- If you want to use smaller text, you should use the beamer documentclass options:
  - `smaller` (I think this is 10pt). Things should stay OK.
  - `9pt`. In this case, beamer makes titles smaller, and the package counteracts this. Also, the right margins are smaller by the package, such that you can pack more on the slide. 

## Caveats

- Because of LuaTeX, packages `fontenc`, `inputenc`, `textcomp` should not be loaded
- Load `amsmath` before `PSI43` (because the package loads `fontspec`)
- The package loads the following packages: `fontspec`
- LuaTeX needs a little bit longer to compile
