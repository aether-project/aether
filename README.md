### How To Compile

#### Ubuntu 16.04+ and MacOS 10.10+

### Linux requirements

Easy to use dependencies installation script (tested on Ubuntu 16.04 64 Bit):
https://github.com/aether-project/aether/blob/master/install_dependencies.sh

#### Windows 10

### Windows requirements

1. Install MinGW (default install) <br />
http://sourceforge.net/projects/mingw/files/Installer/mingw-get-setup.exe/download
  * Select 'msys-base' from the install options
  * Select 'msys-patch (bin)' and 'msys-zip' from All Packages
  * Select 'Apply changes' from Installation menu
2. Add msys to path by executing the following in command prompt (you must run it as admin):
    ```
    SETX PATH "%PATH%;C:\MinGW\msys\1.0\bin" /M
    ```
3. Install git <br />
http://git-scm.com/download/win
4. Download and install Microsoft Visual Studio Community 2013 for Windows Desktop:<br />
https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx
5. Add path to .NET framework by executing the following in command prompt (you must run it as admin):
    ```
    SETX PATH "%PATH%;C:\Program Files (x86)\MSBuild\12.0\bin\amd64" /M
    ```
6. Download and install boost binaries boost_1_57_0-msvc-12.0-64.exe from http://sourceforge.net/projects/boost/files/boost-binaries into c:\local\boost_1_57_0<br />
http://sourceforge.net/projects/boost/files/boost-binaries/1.57.0/boost_1_57_0-msvc-12.0-64.exe/download
7. Set environmental variables for boost by executing the following in command prompt (you must run it as admin):
    ```
    SETX BOOST_ROOT "C:\local\boost_1_57_0" /M

    SETX BOOST_LIBRARYDIR "C:\local\boost_1_57_0\lib64-msvc-12.0" /M
    ```
8. Install the latest version of Cmake (http://www.cmake.org):<br />
Version in the time of writing:
http://www.cmake.org/files/v3.1.2/cmake-3.2.1-win32-x86.exe
9. Install Python 2.7 (http://python.org):<br />
https://www.python.org/ftp/python/2.7.9/python-2.7.9.amd64.msi

##### Building

- From the start menu, open 'x64 Native Tools Command Prompt for vs2017'.
- `cd <yourAetherDirectory>`
- `mkdir build`
- `cd build`
- Set the PATH variable for cmake: ie. `set PATH="C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin";%PATH%`
- `cmake -G "Visual Studio 14 Win64" .. -DBOOST_ROOT=D:/Boost/boost_1_59_0` (Or your boost installed dir.)
- `MSBuild ByteCoin.sln /p:Configuration=Release /m`
- If all went well, it will complete successfully, and you will find all your binaries in the '..\build\src\Release' directory.
- Additionally, a `.sln` file will have been created in the `build` directory. If you wish to open the project in Visual Studio with this, you can.


#### Apple

##### Prerequisites

- Install [cmake](https://cmake.org/). See [here](https://stackoverflow.com/questions/23849962/cmake-installer-for-mac-fails-to-create-usr-bin-symlinks) if you are unable call `cmake` from the terminal after installing.
- Install the [boost](http://www.boost.org/) libraries. Either compile boost manually or run `brew install boost`.
- Install XCode and Developer Tools.

Easy to use dependencies installation script:
https://github.com/aether-project/aether/blob/master/install_dependencies.sh

##### Building

- `git clone https://github.com/aether-project/aether`
- `cd aether`
- `mkdir build && cd $_`
- `cmake ..` or `cmake -DBOOST_ROOT=<path_to_boost_install> ..` when building
  from a specific boost install
- `make`

The binaries will be in `./src` after compilation is complete.

#### Thanks
Cryptonote Developers, Bytecoin Developers, Monero Developers, Forknote Project
