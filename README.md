# Benchmarking with brian2

```bash
# Build
docker build -t brian2-benchmark .

# Run
docker run -t --rm brian2-benchmark

# To debug
docker run -it --rm brian2-benchmark /bin/bash

# Get results on first machine
docker run -t --rm brian2-benchmark > results/cpu1.txt
# Get results on second machine
docker run -t --rm brian2-benchmark > results/cpu2.txt
# ...
# Format results in Markdown
ruby format_results.rb results/*
```

Brian-2 benchmarks are taken from the [ModelDB record #222725](https://senselab.med.yale.edu/ModelDB/showmodel?model=222725#tabs-1) and associated with the paper [Software for Brain Network Simulations: A Comparative Study](https://www.frontiersin.org/articles/10.3389/fninf.2017.00046/full)

## Hardware platforms

1. MacBook Pro 13" M1 (2020, 16GB RAM)
  - M1
    - 8 cores (4 performance, 4 efficient)
    - CPU TDP 15W (?)
  - VM, Docker for Mac 4.12.0, configured to 8 Cores, 8GB RAM, `virtualization.framework`
  - macOS Monterey 12.5.1
2. MacBook Pro 14" M1 Max 10CPU 32GPU (2021, 64GB RAM)
  - M1 Max
    - 10 cores (8 performance, 2 efficient)
    - CPU TDP ~30W (?)
  - VM, Docker for Mac 4.12.0, configured to 10 Cores, 16GB RAM, `virtualization.framework`
  - macOS Monterey 12.5.1
3. MacBook Air M2 8CPU 10GPU (2022, 24GB RAM)
  - M2
    - 8 cores (4 performance, 4 efficient)
    - CPU TDP 15W (?), passive cooling
  - VM, Docker for Mac 4.12.0, configured to 8 Cores, 8GB RAM, `virtualization.framework`
  - macOS Monterey 12.5.1
4. FrameWork 2021
  - 11th Gen Intel(R) Core(TM) i7-1165G7 @ 2.80GHz
    - 4 cores / 8 threads
  - Docker version 20.10.14, build a224086
  - Pop!_OS 22.04 LTS

## Tests

1. 5000 Leaky Integrate-and-File neurons in a sparsely connected network.
2. 500 Hodgkin-Huxly neurons with double-exponential synapses and random connections

## Results

![Graphs with results](results.jpg?raw=true )
