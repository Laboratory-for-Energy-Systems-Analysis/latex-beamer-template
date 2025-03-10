# LaTeX template for PSI slide presentations

## Usage restriction

Only for internal use by PSI employees for scientific presentations that require a lot of mathematics and cannot be done with the official PowerPoint template.


## New version (July 2024): Updated to new CI of PSI

### Usage

Copy all the files and the font-folder ("Aptos") to an Overleaf project, or to your PC.

See "example.tex":

* The default PSI cloud version on the title page is the "blue" one. Options: "Red", "DarkBlue", and "Blue". 
* The default center is "CEE". Options: "CEE", "CAS", "CCS", "CLS", "CNM", "CPS", "NES", "SCD".

If you want to change the footer text, use "\renewcommand{\PSIcenter}{my new text}".

If you use Overleaf, you need (at last currently) the Aptos-font (which is provided in the Aptos-folder). 

Note that because of the use of this non-LaTeX font, you have to choose as compile engine "LuaTeX" or "XeTeX" instead of the usual "pdfTeX". This can be easily switched in Overleaf.

For more info, look into "PSI.sty".

#### Future developments

- depends on user needs
