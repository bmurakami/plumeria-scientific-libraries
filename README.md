# Plumeria Scientific Libraries

Plumeria Scientific Libraries (PluSciLib) provides prebuilt static C libraries for supported Linux and macOS architectures. The current release artifacts provide BLAS and LAPACK through OpenBLAS.

## Quick Start

Download the release archive that matches your platform. For example:

```sh
curl -L "https://github.com/bmurakami/plumeria-scientific-libraries/releases/download/0.1-latest/pluscilib-darwin-m1.tar.gz" -o pluscilib.tar.gz
mkdir pluscilib
tar -xzf pluscilib.tar.gz -C pluscilib
```

The extracted archive is laid out like an install prefix. Expect headers under `include/` and static
libraries under `lib/`, including `libopenblas.a`.

## Release Files

| Release file | Platform | Target |
| --- | --- | --- |
| `pluscilib-darwin-m1.tar.gz` | macOS | Apple Silicon |
| `pluscilib-linux-aarch64.tar.gz` | Linux | generic `aarch64` |
| `pluscilib-linux-neoverse_v2.tar.gz` | Linux | `neoverse_v2` |
| `pluscilib-linux-x86_64.tar.gz` | Linux | generic `x86_64` |

All current release files contain static OpenBLAS builds: `openblas@0.3.33 shared=false`.

## Optional Local Build

Local builds are not required to use PluSciLib. For those who want to explore or add new build targets, Spack is a required tool. 

To build a target, activate a Spack environment for your target and install it. For example:

```sh
spack env activate --dir spack-environments/linux-x86_64
spack install
```

Spack will place the build in a Spack "view".

```text
spack-environments/linux-x86_64/.spack-env/view/
```
