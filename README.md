AI for the [2048 4D game](http://huonw.github.io/2048-4D/). This uses *expectimax optimization*, along with a highly-efficient bitboard representation to search upwards of 10 million moves per second on recent hardware. Heuristics used include bonuses for empty squares and bonuses for placing large values near edges and corners.

## Building

### Unix/Linux/OS X

Execute

    ./configure
    make

in a terminal. Any relatively recent C++ compiler should be able to build the output.

Note that you don't do `make install`; this program is meant to be run from this directory.

### Windows

You have a few options, depending on what you have installed.

- Pure Cygwin: follow the Unix/Linux/OS X instructions above. The resulting DLL can *only* be used with Cygwin programs, so
to run the browser control version, you must use the Cygwin Python (not the python.org Python). For step-by-step instructions, courtesy Tamas Szell (@matukaa), see [this document](https://github.com/nneonneo/2048-ai/wiki/CygwinStepByStep.pdf).
- Cygwin with MinGW: run

        CXX=x86_64-w64-mingw32-g++ CXXFLAGS='-static-libstdc++ -static-libgcc -D_WINDLL -D_GNU_SOURCE=1' ./configure ; make

    in a MinGW or Cygwin shell to build. The resultant DLL can be used with non-Cygwin programs.
- Visual Studio: open a Visual Studio command prompt, `cd` to the 2048-ai directory, and run `make-msvc.bat`.

## Running the command-line version

Run `bin/2048` if you want to see the AI by itself in action.

## Running the browser-control version

Install [Remote Control for Firefox](https://github.com/nneonneo/FF-Remote-Control/raw/V_1.2/remote_control-1.2-fx.xpi).

Open up the [2048 4D game](http://huonw.github.io/2048-4D/) and start remote control.

Run `2048.py` and watch the game!
