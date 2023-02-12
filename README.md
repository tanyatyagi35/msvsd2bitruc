# msvsd2bitruc-(2bit_ripple_upcounter_with_555timer_AstableMultivibrator_As_clock_circuit)
# VSD Mixed-signal PD Research Program

# Week0 Tasks:


1. Installation of openSource Tools and SKY130 PDKs

STEP1: TO START WITH CREATION OF VSD FLOW
```
$ sudo apt-get install git
```

STEP2: FOR MAGIC INSTALLATION
Magic is an open-source VLSI layout tool. Its installation process includes following steps:
```
$ git clone git://opencircuitdesign.com/magic
$ cd magic
// Install M4 preprocessor
$ sudo apt-get install m4       
// Install tcsh shell
$ sudo apt-get install tcsh   
// Install csh shell
$ sudo apt-get install csh         
// Install xlib
$ sudo apt-get install libx11-dev  
//If you wish to have the Tcl/Tk wrapper around magic (recommended) you will need to install the Tcl/Tk libraries.
$ sudo apt-get install tcl-dev tk-dev
// Cairo graphics interface
$ sudo apt-get install libcairo2-dev
// The OpenGL interface
$ sudo apt-get install mesa-common-dev libglu1-mesa-dev
// ncurses library 
$ sudo apt-get install libncurses-dev
$ ./configure
$ make
$ sudo make install
```
More info can be found at http://opencircuitdesign.com/magic/index.html


STEP3: FOR NETGEN INSTALLATION
Netgen is a tool for comparing netlists, a process known as LVS, which stands for "Layout vs. Schematic". Its installation process includes following steps:
```
$  git clone git://opencircuitdesign.com/netgen
$  cd netgen
$  ./configure
$  make
$  sudo make install
```
More info can be found at http://opencircuitdesign.com/netgen/index.html


STEP4: FOR XSCHEM INSTALLATION
Xschem is a schematic capture program. Its installation process includes following steps:
```
$  git clone https://github.com/StefanSchippers/xschem.git xschem_src
$   cd xschem-src
// Install flex and bison
$  sudo apt-get install -y flex bison
// Install flex and bison
$  sudo apt-get install -y flex bison
// Install libjpeg-dev 
$  sudo apt-get -y install libjpeg-dev
// Install xcb
$  sudo apt-get -y install xcb
$  ./configure
$  make
$  sudo make install
```
More info can be found at http://repo.hu/projects/xschem/index.html


STEP5: FOR NGSPICE INSTALLATION
ngspice is the open-source spice simulator for electric and electronic circuits. Download ngspice-39 tarball ngspice-39.tar.gzfrom https://ngspice.sourceforge.io/download.html into the work directory and then its installation process includes following steps:
```
$  tar -xzvf ngspice-39.tar.gz
$  mkdir release
$  cd release 
// Update the system
$  sudo apt-get update
// Install Xaw library
$  sudo apt-get -y install libxaw7-dev
// Install xterm
$  sudo apt-get -y install xterm
// Install bison
$  sudo apt-get -y install bison
// Install flex
$  sudo apt-get -y install flex
// Install readlines library
$  sudo apt-get -y install libreadlines6-dev
$  ../configure  --with-x --with-readline=yes --disable-debug
$  make 
$  sudo make install
// In order to view the simulation graphs of ngspice, xterm is required and can be installed using:
$  sudo apt-get update
$  sudo apt-get install xterm
```
More info can be found at https://ngspice.sourceforge.io/index.html


STEP6: FOR OPEN_PDKs INSTALLATION
Open_PDKs is distributed with files that support the Google/SkyWater sky130 open process description https://github.com/google/skywater-pdk. Open_PDKs will set up an environment for using the SkyWater sky130 process with open-source EDA tools and tool flows such as magic, qflow, openlane, netgen, klayout, etc. Its installation process includes following steps:
```
// Install setup-tools
$  sudo apt-get -y install python3-setuptools
$  git clone git://opencircuitdesign.com/open_pdks
$  cd open_pdks
$  ./configure --enable-sky130-pdk
$  make 
$  sudo make install
```
   
STEP7: FOR ALIGN INSTALLATION
ALIGN is an open source automatic layout generator for analog circuits. Its installation process includes following steps:
```
$  git clone https://github.com/ALIGN-analoglayout/ALIGN-public
$  cd ALIGN-public
// Install virtual environment for python
$  sudo apt -y install python3.8-venv
// Install the latest pip
$  sudo apt-get -y install python3-pip
// Create python virtual envronment
$  python3 -m venv general
$  source general/bin/activate
$  python3 -m pip install pip --upgrade
$  pip install align
$  pip install pandas
$  pip install scipy
$  pip install nltk
$  pip install gensim
$  pip install setuptools wheel pybind11 scikit-build cmake ninja
// Install ALIGN as a user
$  pip install -v .
// Install ALIGN  as a developer
$  pip install -e .
$  pip install -v -e .[test] --no-build-isolation
$  pip install wheel setuptools pip --upgrade
$  pip3 install wheel setuptools pip --upgrade
$  pip install -v --no-build-isolation -e . --no-deps --install-option='-DBUILD_TESTING=ON'
```

For making ALIGN Portable to Sky130 tehnology, clone the following Repository inside ALIGN-public directory
```
$  git clone https://github.com/ALIGN-analoglayout/ALIGN-pdk-sky130
```
Move SKY130 PDK folder to ALIGN-public/pdks. Everytime we start the tool in new terminal, run the following commands.

