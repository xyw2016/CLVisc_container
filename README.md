# CLVisc Singularity Container

This is a **Singularity container** for running the **CLVisc framework**, preconfigured with key high-energy physics tools and libraries. It includes:

- **Pythia 8.303** – compatible with **SMASH 2.2**
- **Pythia 8.309** – compatible with **SMASH 3.0**
- **OpenCL**, **Python 3.11**, **PyOpenCL**, **Boost**, **GSL**, **HDF5**, **Eigen 3.4.0**, **GCC 9**, and other development tools.

---
It is easy to use:
##  1. Pull the Container

Pull the container from [Sylabs Cloud](https://cloud.sycloud.io):

```bash
apptainer remote add --no-login SylabsCloud cloud.sycloud.io
singularity pull --arch amd64 library://xiangyuwu/hydro/clviscdev:stable
```

### 2. Run the container with NVIDIA GPU support and bind the host CUDA and OpenCL configuration:

```bash
singularity shell --nv \
  --bind /path/to/your/cuda:/usr/local/cuda \
  --bind /etc/OpenCL/vendors:/etc/OpenCL/vendors \
  ./clviscdev_latest.sif
```

**Replace** `/path/to/your/cuda` with the actual path to your CUDA installation  
> (for example: `/usr/local/cuda-11.4`)
