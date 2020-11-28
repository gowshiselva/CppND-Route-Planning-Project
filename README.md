# Route Planning Project

This project, i have done as part of my course work in udacity nanodegree programme. I have implemented A* route planning algorithm in this work. This algorithms
is wildly used in map services like google map.

This algorithm can be used to find the shortest path between two points. In this programme, coordinates are entered as userinput between 0 and 100. Then, the io2d library is used to darw the line and shortest path is rendered to the map.

<img src="map.png" width="600" height="450" />






## Dependencies for Running Locally
* cmake >= 3.11.3
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 7.4.0
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same instructions as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* IO2D
  * Installation instructions for all operating systems can be found [here](https://github.com/cpp-io2d/P0267_RefImpl/blob/master/BUILDING.md)
  * This library must be built in a place where CMake `find_package` will be able to find it

## install IO2D
## Install and Build IO2D

Installation instructions for all operating systems can be found [here](https://github.com/cpp-io2d/P0267_RefImpl/blob/master/BUILDING.md). This library must be built in a place where CMake `find_package` will be able to find it.

###  Using _COREGRAPHICS/MAC_ to compile and build IO2D

* Change directory into the repo and `cd` into `thirdparty` folder and download IO2D files:
```
git clone --recurse-submodules https://github.com/cpp-io2d/P0267_RefImpl
```

* Xcode currently comes with an old version of libc++ which lacks many of C++17 features required by IO2D. The easiest solution is to download a fresh build of libc++ from [here](http://releases.llvm.org/6.0.0/clang+llvm-6.0.0-x86_64-apple-darwin.tar.xz). Export appropriate CXX and LD flags to make clang use this version of the standard library (replace <*NEWPATH*> with path of extracted archive contents):
```
export CXXFLAGS="-nostdinc++ -isystem<NEWPATH>/include/c++/v1"
export LDFLAGS="-L<NEWPATH>/lib -Wl,-rpath,<NEWPATH>/lib"
```

* Install HomeBrew package manager:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```
* Install cmake:  `brew install cmake`
* Install make: `brew install make`
* Install pkg-config: `brew install pkg-config`
* Install libpng:  `brew install libpng`
* Install graphicsmagick: `brew install graphicsmagick`
* Install [MacPorts](https://www.macports.org/install.php), since Brew doesn't have Cairo.
* Install Cairo: `sudo /opt/local/bin/port -N -k install cairo +x11`

* Update $PATH environment variable for Brew (whereas, MacPort does it automatically):
```
echo `export PATH="$(brew --prefix)/opt/make/libexec/gnubin:$PATH"` >> ~/.bash_profile
```

*  `cd` into `P0267_RefImpl` (in `thirdparty`),  and inside new `Debug` folder build and open the IO2D Xcode project:
```
mkdir Debug && cd Debug
cmake -G "Xcode" --config Debug "-DCMAKE_BUILD_TYPE=Debug" -DIO2D_DEFAULT=COREGRAPHICS_MAC ../.
open io2d.xcodeproj
```

## Compiling and Running

### Compiling
To compile the project, first, create a `build` directory and change to that directory:
```
mkdir build && cd build
```
From within the `build` directory, then run `cmake` and `make` as follows:
```
cmake ..
make
```
### Running
The executable will be placed in the `build` directory. From within `build`, you can run the project as follows:
```
./OSM_A_star_search
```
Or to specify a map file:
```
./OSM_A_star_search -f ../<your_osm_file.osm>
```

## Testing

The testing executable is also placed in the `build` directory. From within `build`, you can run the unit tests as follows:
```
./test
```

