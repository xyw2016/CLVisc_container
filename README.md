# CLVisc Singularity Container

This is a **Singularity container** for running the **CLVisc framework**, preconfigured with key high-energy physics tools and libraries. It includes:

- **Pythia 8.303** – compatible with **SMASH 2.2**
- **Pythia 8.309** – compatible with **SMASH 3.0**
- **OpenCL** (host-provided), **Python 3.11**, **PyOpenCL 2025.01**, **NumPy 1.24.3**, **h5py**, **SciPy**, **Pandas**, **Matplotlib**,  
  **Boost 1.71.0**, **GSL**, **HDF5 (via libhdf5-dev)**, **Eigen 3.4.0**, **GCC/G++ 9**, and other development tools (e.g., CMake 3.16, Git, Vim).


---
It is easy to use:
##  1. Pull the Container

Pull the container from [Sylabs Cloud](https://cloud.sycloud.io):

```bash
apptainer remote add --no-login SylabsCloud cloud.sycloud.io
singularity pull --arch amd64 library://xiangyuwu/hydro/clviscdev:stable
```

### 2. Run the Container

Run the container with NVIDIA GPU support and bind the host CUDA and OpenCL configuration:

---
```bash
singularity shell --nv \
  --bind /path/to/your/cuda:/usr/local/cuda \
  --bind /etc/OpenCL/vendors:/etc/OpenCL/vendors \
  ./clviscdev_stable.sif
```

**Replace** `/path/to/your/cuda` with the actual path to your CUDA installation  
(for example: `/usr/local/cuda-11.4`)
