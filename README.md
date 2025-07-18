# gr-ysf

# This is a kinda hacky fix to get [gr-ysf](https://github.com/HB9UF/gr-ysf) built on modern systems, there are some small code changes, and I removed the unit tests which used deprecated libraries and I didn't want to re-write them.
# Unfortunatly I think that this still requires an old version of gnu radio because it produces xml based blocks, which are now deprecated.

## it compiles, but the blocks won't load, at least not on the latest gnuradio version, I have no idea if this still works on the version it was written for, 3.7.5.



GNU Radio modules for decoding Yaesu System Fusion C4FM packets

See the following link for information on the project:

http://hb9uf.github.io/gr-ysf/

## Prerequisites

In addition to GNU Radio and gr-osmosdr, you need a C++ compiler, cmake, swig
and mbelib to successfully compile this project. The code was tested with g++
4.8.4, cmake 2.8.12.2, GNU Radio 3.7.5, swig 2.0.11 and mbelib 1.2.5.

```
sudo apt install libboost-system-dev libboost-filesystem-dev libboost-dev
```

## Compiling
Compiling the project is straight forward and similar to other GNU Radio out of
tree modules. Run the following inside the project root directory:

```
mkdir build
cd build
cmake ..
make
```

Then as root, run the following inside the `build` directory that you created
and entered in the previous step:

```
make install
ldconfig
```

You should now be able to load and run `examples/ysf_rx.grc` in
`gnuradio-companion`.
