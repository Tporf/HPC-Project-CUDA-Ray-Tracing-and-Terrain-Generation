# HPC Project: Benchmarking of CUDA Ray Tracing written in different languages

## Languages Used

- **CUDA C++**  
  Core kernels implementation for high-performance tasks such as ray tracing leveraging GPU massive parallelism.  
  Example: CUDA ray tracer from [NVIDIA blog](https://developer.nvidia.com/blog/accelerated-ray-tracing-cuda/) and [GitHub repo](https://github.com/Ancientkingg/cuda-raytracer)[1][2].

- **Python**  
  Hand written implementations of ray traysing in form of sequential, CUDA parallel with cupy functions and CUDA parallel with cupy kernel.
  GPU parallelism was achieved using [CuPy](https://cupy.dev/).

---

## Key HPC Concepts

### Massive Parallelism in CUDA Kernels

- CUDA executes thousands of lightweight threads organized in blocks and grids.
- Each thread handles one or more pixels or computation units (rays in ray tracing)..

### Memory Management

- **Global Memory:** Large but high latency; minimize accesses and coalesce memory reads/writes.
- **Shared Memory:** Fast on-chip memory shared by threads in the same block; use for data reuse and reducing global memory traffic.
- **Constant Memory:** Cached read-only memory for frequently used constants (e.g., scene parameters).
- Proper memory hierarchy usage is critical for performance.

### CPU vs GPU Comparison

- Implement CPU baseline without any parallelism to have a clear view at a start point.
- Compare performance and scalability against CUDA GPU implementations.

### Profiling and Optimization

- Identify bottlenecks such as memory bandwidth, occupancy, and divergent branches.
- Optimize kernel launch configuration, memory access patterns, and use asynchronous data transfers.
