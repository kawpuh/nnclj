# nnclj
Clojure implementation of [Neural Networks and Deep Learning](neuralnetworksanddeeplearning.com)

The original python2 implementation can be found [here](https://github.com/mnielsen/neural-networks-and-deep-learning)

The easiest way I could find to get my hands on the MNIST dataset was from [Kaggle](https://www.kaggle.com/datasets/oddrationale/mnist-in-csv)

# Thoughts
- lazy evaluation and easy concurrency with pmap is nice
- core.matrix with the vectorz implementation is fast
- however vectorz is built around doubles
  - losing some speed since we can't take advantage of SIMD instructions with 2x parallelism for fp32 vs fp64
- should use CUDA anyways 
  - for my hardware we'd have theoretical ~10x performance on CUDA using fp32
- in general fp32 is awkward in clojure because builtin math operations convert to clojure.lang.Number which uses double-precision floats
