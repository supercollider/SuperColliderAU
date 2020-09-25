SuperColliderAU
===============

SuperColliderAU is an AudioUnit wrapper that allows using SuperCollider servers inside AudioUnits hosts on macOS. The embedded server may be controlled over OSC as usual. In addition, it may be packed with a synth definition and a configuration file that defines its parameters.

Below are some quick instructions for building SuperColliderAU. The result is an AudioUnit plug-in that can be used for the first use case (interactive), and can also be modified for the second (standalone) using the AudioUnitBuilder quark.

In order to build SuperColliderAU, you first need to build SuperCollider, which is included in this repository as a submodule. For this to work you must first clone the SuperColliderAU with the recursive flag:

git clone --recursive https://github.com/supercollider/SuperColliderAU

After this, cd to the supercollider directory and build as explained in the Build Instructions section in README_MACOS.md. This is needed for generating `SC_Version.hpp` and also for compiling plugins. It is important to note that the build process for SuperColliderAU assumes that the name of the supercollider build folder `build`.

After compiling SuperCollider, cd back to the SuperColliderAU root directory and run:

    mkdir build
    cd build
    cmake ..
    make

If everything goes well this should create a bundle named SuperColliderAU.component. To use, copy the bundle to ~/Library/Audio/Plug-Ins/Components/.
