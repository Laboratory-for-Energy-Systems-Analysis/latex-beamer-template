# PSI LaTeX template for slide presentations

- uses LaTeX's "beamer" class
- an example output is in the file `PSI_test.pdf`; it is not (yet) perfect
- currently supported format is the old 4:3 aspect ratio (and not 16:9)
- You need to select the LuaTeX engine to compile to a pdf file (perhaps XeTeX would also work). If you use Overleaf, you have to change the compiler [Overleaf, Compiler](https://www.overleaf.com/learn/how-to/Changing_compiler)
   Reason: The common pdfTeX engine cannot use system fonts (Calibri, Georgia).
   
I am aware that some time ago somebody else from PSI made a template. What are the differences:

- This is just a simple, lightweight package. It does not load other packages apart from the "fontspec" package from LuaTeX, which is needed because of the fonts.
- There is no inner, outer theme defined etc. It is just the default beamer theme

## Usage

1. Place the three files PSI43.sty, PSIlandscape.jpg, PSI.pdf in your folder of your presentation LaTeX file (or somewhere where LaTeX can find it)
2. Use `\usepackage{PSI43}` in our file, see the example file `PSI_test.tex`
3. Use `\documentclass[aspectratio=43]{beamer}`, in fact `43` should be the default


## Caveats

- Because of LuaTeX, packages `fontenc`, `inputenc`, `textcomp` should not be loaded.
- The package loads `fontspec`
- LuaTeX needs a little bit longer to compile
