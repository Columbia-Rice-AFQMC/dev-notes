# Profiling applications with `nsys`

1. Compile with `profile` target
```
make cleanall
make profile
```
2. Copy the config file `nsys_profile.conf` to the runtime directory.
3. Run and profile the codes
```
nsys profile --command-file=nsys_profile.conf <executable>
```
This will generate a `nsys-rep` report that can later be visualize in [Nsight Systems](https://developer.nvidia.com/nsight-systems), with custom NVTX markers for events we want to profile, along with all the other CUDA/CUBLAS API timings.

Additionally, you can also generate statistics from the report by running `nsys stats`. For more details about possible options, run with the `--help` option or checkout the [documentation](https://docs.nvidia.com/nsight-systems/UserGuide/index.html).