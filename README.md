VSD Mixed-signal PD Research Program
# msvsd2bitruc-(2bit_ripple_upcounter_with_555timer_AstableMultivibrator_As_clock_circuit)


# Week0 Tasks:


# 1. Installation of openSource Tools and SKY130 PDKs

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


# 2. Verifiying Open PDKs installation and tools testing

STEP1: Verifiying Open PDKs installation

![Screenshot from 2023-02-12 01-32-26](https://user-images.githubusercontent.com/30209235/218304616-e17d01e0-b6bd-4b03-b1de-1ecae45a2f52.png)

STEP2: Magic Test

![Screenshot from 2023-02-12 13-46-22](https://user-images.githubusercontent.com/30209235/218304877-48a3ce5d-08ca-4f59-a7e0-7fa7be939edc.png)

STEP3: Xschem Test

![Screenshot from 2023-02-12 13-47-33](https://user-images.githubusercontent.com/30209235/218304859-2f872e96-284d-4d90-a818-7cf44f417788.png)

STEP4: Netgen Test

![Screenshot from 2023-02-12 13-48-11](https://user-images.githubusercontent.com/30209235/218304902-89574d4c-8c08-42e8-9d14-35d2d61da3d1.png)

# 3.1 Inverter Schematic creation using xschem

![Screenshot from 2023-02-12 16-23-38](https://user-images.githubusercontent.com/30209235/218313865-8234a393-f0ee-4398-9746-3f16e21b19e6.png)

# 3.2 Inverter Symbol creation using xschem

![Screenshot from 2023-02-12 16-24-32](https://user-images.githubusercontent.com/30209235/218313945-4c11c9e9-bbe7-4f37-9a41-bd7821801cf0.png)

# 3.3 Inverter Testbench creation using xschem

![Screenshot from 2023-02-12 18-16-06 (1)](https://user-images.githubusercontent.com/30209235/218314052-e721e51a-d3d4-45fd-a029-ea1ca6d20247.png)

# 3.4 inverter_tb.spice Netlist

![Screenshot from 2023-02-12 18-15-51](https://user-images.githubusercontent.com/30209235/218314306-661d197e-089b-49ca-a639-be742fb6d90d.png)

![Screenshot from 2023-02-12 18-15-57](https://user-images.githubusercontent.com/30209235/218314265-29473fe6-ec48-4f58-9080-129737a242f9.png)

# 3.5 Simulating netlist using Ngspice

![Screenshot from 2023-02-12 18-18-42 (1)](https://user-images.githubusercontent.com/30209235/218314432-81a4fdef-6228-48b7-8b16-7ade29e7edc1.png)

# 3.6 Waveform obatined

![Screenshot from 2023-02-12 18-18-29](https://user-images.githubusercontent.com/30209235/218314460-97854039-80fb-46f5-a9ea-f615417cb66f.png)







