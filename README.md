# Benchmarking with brian2

```bash
# Build
docker build -t brian2-benchmark .

# Run
docker run -t --rm brian2-benchmark

# To debug
docker run -it --rm brian2-benchmark /bin/bash
```

Brian-2 benchmarks are taken from the [ModelDB record #222725](https://senselab.med.yale.edu/ModelDB/showmodel?model=222725#tabs-1) and associated with the paper [Software for Brain Network Simulations: A Comparative Study](https://www.frontiersin.org/articles/10.3389/fninf.2017.00046/full)
