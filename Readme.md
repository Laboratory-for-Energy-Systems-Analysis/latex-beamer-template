# LaTeX template for PSI slide presentations

## Usage restriction

Only for internal use by PSI employees for scientific presentations that require a lot of mathematics and cannot be done with the offical powerpoint template.


## New version (June 2024): Updated to new CI of PSI

### Usage

Copy all the files and the font-folder ("Aptos") to an Overleaf project, or to your PC.

Currently, the PSI cloud version is the "blue" one, and the center is "EES". If you use another center, or another cloud color, adapt the filenames (picture-files (.png), copied from Powerpoint master-slide) in the preamble of the LaTeX file.

If you use Overleaf, you currently still need the Aptos-font (which is provided in the Aptos-folder). 

Note that because of the use of the non-LaTeX font Aptos, you have to choose as compile engine "LuaTeX" or "XeTeX" instead of the usual "pdfTeX". 

For more info, look into the comments in the LaTeX preamble of main.tex.

#### Future developments

* If the preamble is fully parametrized eventually, one could put the preamble in a LaTeX style file (and invoke it by usepackage). On the other side, this creates a black box.  
