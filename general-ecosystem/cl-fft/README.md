# cl-fft: Pure Cluster Cooley-Tukey Radix-2 Fast Fourier Transform

> **Author**: zk-mohammad <ZaidKhan-alamgir@proton.me>  
> **License**: CCFL v2.0  
> **Repository**: `modules/cl-fft`  

A 100% pure Cluster implementation of the Cooley-Tukey Radix-2 Fast Fourier Transform (FFT) algorithm for audio analysis, spectral decomposition, and digital signal processing (DSP).

Zero `cpp_inject`, zero `extern "C"`, zero external dependencies.

## Features
- **Radix-2 Cooley-Tukey Algorithm**: Forward and Inverse FFT executing in $O(N \log N)$ complexity.
- **Complex Number Subsystem**: Complete algebraic operations (addition, subtraction, multiplication, and magnitude).
- **Bit-Reversal Permutation**: Fast in-place data re-ordering.
- **Spectral Decomposition**: Calculates spectral magnitudes and frequency bin energy.

## Quickstart

```cluster
import "cl-fft/fft.zk"

fn main():
    // 8-sample audio or sensor signal
    samples: vector[float] := [1.0, 1.0, 1.0, 1.0, 1.0, 1.0, 1.0, 1.0]
    res := fft_forward(samples)

    dc_energy := res.magnitudes[0] // 8.0
    original  := fft_inverse(res)  // Reconstructs original samples
```
