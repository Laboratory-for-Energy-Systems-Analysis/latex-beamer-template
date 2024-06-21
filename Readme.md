# LaTeX template for PSI slide presentations

## Usage restriction

Only for internal use by PSI employees for scientific presentations that require a lot of mathematics and cannot be done with the offical powerpoint template.


## New version (June 2024): Updated to new CI of PSI

### Usage

Copy all the files and the font-folder ("Aptos") to an Overleaf project, or to your PC.

In "main.tex", the PSI cloud version on the title page is the "blue" one, and the center logo is for "CEE". If you use others, adapt the filenames (which point to the picture-files (.png), copied from Powerpoint master-slide) in the preamble of the LaTeX file, and adapt also the footer text.

If you use Overleaf, you need (at last currently) the Aptos-font (which is provided in the Aptos-folder). 

Note that because of the use of this non-LaTeX font, you have to choose as compile engine "LuaTeX" or "XeTeX" instead of the usual "pdfTeX". This can be easily switched in Overleaf.

For more info, look into the comments in the LaTeX preamble of main.tex.

#### Future developments

* If the preamble will be fully parametrized eventually, one could put the preamble in a LaTeX style file (and invoke it by usepackage). On the other side, this creates a black box.  
