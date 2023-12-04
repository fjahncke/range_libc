# RangeLibc

This library provides for different implementations of 2D raycasting for 2D occupancy grids, including the Compressed Directional Distance Transform (CDDT) algorithm as proposed in [this publication](http://arxiv.org/abs/1705.01167). The code is written and optimized in C++, and Python wrappers are also provided.

<!-- WARNING: this is currently in a slightly weird state in preparation for 6.141 lab 5. I will try to fix up all the compile flags to work with both use cases soon. -->

## Building the Code

The following has been tested on Ubuntu 20, ROS2 Foxy, and the Jetson Orin Nano.

### Building on a RACECAR

MIT's 6.141 uses this library for accelerating particle filters onboard the RACECAR platform. To install this on the Jetson Orin Nano, do:

```
# Copy the code
sudo apt-get install ros-foxy-tf-transformations
sudo apt-get install cython
pip3 install transforms3d
git clone https://github.com/f1tenth/range_libc.git
cd range_libc
mkdir build
cd build
cmake ..
make
cd ~/range_libc/pywrapper
sudo WITH_CUDA=ON python setup.py install #for python2.7
sudo WITH_CUDA=ON python3 setup.py install #for python3.8
```

## License

This code is licensed under Apache 2.0. Copyright 2017 Corey H. Walsh. 

You may obtain a copy of the License at: http://www.apache.org/licenses/LICENSE-2.0

Enjoy!

## Cite

This library accompanies the following [publication](http://arxiv.org/abs/1705.01167).

    @article{walsh17,
        author = {Corey Walsh and 
                  Sertac Karaman},
        title  = {CDDT: Fast Approximate 2D Ray Casting for Accelerated Localization},
        volume = {abs/1705.01167},
        url    = {http://arxiv.org/abs/1705.01167},
        year   = {2017}}


## References

1.  J. Bresenham. "Algorithm for Computer Control of a Digital Plotter," IBM Systems Journal, vol. 4, no. 1, pp. 25-30, 1965.
2.  K. Perlin and E. M. Hoffert. "Hypertexture," Computer Graphics, vol 23, no. 3, pp. 297-306, 1989.
3. M. Pharr, and R. Fernando. "Chapter 8. Per-Pixel Displacement Mapping with Distance Functions" in GPU gems 2: Programming techniques for high-performance graphics and general-purpose computation, 3rd ed. United States: Addison-Wesley Educational Publishers, 2005.
