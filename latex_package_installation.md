Installation of a LaTex package on Linux (UBUNTU)
===================================================
1. Find the location of latex binary that is used for compiling LaTex using command:
  ``` which latex ``` 
  suppose the output is ```/usr/bin/latex```. Verify that this location contains the actual binary (the output may be a symbolic link - shortcut) by using ```file <file_to_verify>```. Use ``ls -alh <file_to_verify>`` to find the location of binary file if the outpute of previous command is a symbolic link or a shortcut.
 
    * ```lrwxrwxrwx 1 root root 6 Aug 21  2017 /usr/bin/latex -> pdftex``` is a symbolic link (notice the 'l' at the beginning of directory information).

    * ```-rwxr-xr-x 1 root root 700K Oct  9 14:56 /usr/bin/pdftex``` is an actual file

2. Download the package archive and extract.

3. Go to location of the LaTex folder e.g. ```/usr/share/texlive/texmf-dist/tex/latex``` and make a directory with the package name.

4. Copy the package style (.sty) files to the created directory.

5. Run command ``sudo texhash`` to update.



References:
1. https://libguides.uakron.edu/latex/packages