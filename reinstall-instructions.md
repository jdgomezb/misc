# Step by step instruction to get a new Mac ready

* Go to security and privacy and turn on file vault encrypt 

* Allow apps to download from  “Anywhere”

* Change computer name in system preference. I call it macrafa

* Change system preferences to automatically hide dock

* Go to mission control (f3) and add spaces (look up at the corner for + sign)

* Optional: Change shortcut for spotlight to option-space (system preferences search for shortcut)

* Turn off notification
 
* Copy over ~/myDocumnets, ~/Dropbox/ ~/Music/ ~/Pictures/ ~/bin/ ~/Movies/
files from old computer

* Go to the “Keyboard” system preference and change shortcut for moving spaces to command-arrow

* Get rid of "smart" quotes:
	System preferences… > Keyboard > Text > Uncheck “Use smart quotes and dashes”
	TextEdit > Preferences… > Uncheck “smart quotes” and “smart dashes”
	In TextEdit, Edit > Substitutions > Uncheck “Smart Quotes” and “Smart Dashes”

* Install chrome

* install iTerm

* Type git in terminal so mac installs Xtools etc…
	type "brew install git-lfs"
	type "git lfs install"

* install 1password and backup from old files that are here: "~/Library/Application Support/1Password 4"

* Install wget from http://rudix.org/packages/wget.html

* Install R binaries. not sure if i have to do this. but RStudio might R.app to be in the Applicaton folder.

* Optiona: install R from source
	- Install Java JDK from here: http://www.oracle.com/technetwork/java/javase/
	- download gfortran from mac: https://gcc.gnu.org/wiki/GFortranBinaries#MacOS
	- downloads/jdk8-downloads-2133151.html
	- download XZ libraries from: https://sourceforge.net/projects/macpkg/files/XZ/5.0.7/XZ.pkg/download
	- Install with ./configure --with-blas='-framework Accelerate' --with-lapack --without-x --without-internal-tzcode
		make
		sudo make install 

* Install R studio

* install https://tug.org/mactex/mactex-download.html download using safari

* Try to knit with RStudio (PDF) so it installs packages (e.g. knitr)

* Install drop box

* Install R packages from CRAN:

```
install.packages(c("readr","knitr","tidyr","devtools","RColorBrewer","class","caret","gplots","downloader","ggplot2","dplyr","gganimate","ggrepel","animation","UsingR","matrixStats","XML","corpcor"))
```

* Install R packages from Bioc:

```
install.packages("BiocManager")
BiocManager::install(c("genefilter","affy","SpikeIn","SpikeInSubset","limma","hgfocus.db","org.Hs.eg.db","GO.db","DESeq2","bumphunter","minfi","oligo","preprocessCore","qvalue"))
```

* Check what other packages I need after copying over all my coode:
```
find ./ -name "*.[R|Rmd|Rpres]" -exec grep "library" {} \;
```

* Install R packages from github:
```
library(devtools)
install_github(c("ririzarr/rafalib","genomicsclass/tissuesGeneExpression","genomicsclass/GSE5859Subset","genomicsclass/GSE5859"))
```

* Download and install Xquartz from http://xquartz.macosforge.org/landing/


* Download and install microsoft office (ugh) search email for subject line "latest mac os and office"

* Install emacs from http://emacsformacosx.com/

* Install latest ess and put in ~/myDocuments/misc

* Change .emacs to load ess from the dir

* Download markdown-mode.el and put he  ~/myDocuments/misc ess dir
	git clone https://github.com/vspinu/polymode.git in the ess dir

* Install homebrew with 

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

* The latest version of GNU Aspell is 0.60.6.1. Find it at ftp.gnu.org:/gnu/aspell

* Install Xcode command line tools: xcode-select --install

* Install macports: https://www.macports.org/

* Install ImageMagick sudo port install ImageMagick
(instructions from http://cactuslab.com/imagemagick/)
 

* Install printer with IP: 155.52.45.122

* Make ririzarr owner of /usr/local for easy installation using brew sudo chown -R $USER /usr/local

* Install rgdal from 
http://www.compmath.com/blog/2010/07/installing-package-on-mac-os-x/

```		
R CMD INSTALL --configure-args='--with-gdal-config=/Library/Frameworks/GDAL.framework/unix/bin/gdal-config --with-proj-include=/Library/Frameworks/PROJ.framework/unix/include --with-proj-lib=/Library/Frameworks/PROJ.framework/unix/lib --with-proj-data=/Library/Frameworks/PROJ.framework/unix/share/proj --with-data-copy=yes' rgdal_1.1-10.tar.gz
```

* Install rgeos ##for tmap to install
```
R CMD INSTALL rgeos_0.3-19.tar.gz --configure-args="--with-geos-config=/Library/Frameworks/GEOS.framework/unix/bin/geos-config"
```

* aspell for emacs
brew install aspell --with-all-langs
(setq ispell-program-name "aspell") in .emacs
ln -s /usr/local/Cellar/aspell/0.60.6.1/bin/aspell ~/bin/aspell

