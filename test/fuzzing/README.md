# Fuzzing Linkerd

The scripting setup for fuzzing is used by
[google/oss-fuzz](https://github.com/google/oss-fuzz) which performs continuous
fuzzing for the Linkerd project.

The fuzzing configuration for Linkerd is located in the
[linkerd2](https://github.com/google/oss-fuzz/tree/master/projects/linkerd2)
project which handles the docker build and execution of the fuzzers.

## Running locally
Instructions for running the fuzzers locally can be found in the oss-fuzz
[docs](https://google.github.io/oss-fuzz/getting-started/new-project-guide/#testing-locally).

This will require cloning the [oss-fuzz](https://github.com/google/oss-fuzz)
repository locally and running the commands outlined in the instructions.

### oss-fuzz File Setup

- [Dockerfile](https://github.com/google/oss-fuzz/blob/master/projects/linkerd2/Dockerfile)
  provides the necessary environment for running the fuzzer; the main thing
  being the `oss-fuzz-base` image which provides the `compile_go_fuzzer`
  funtions seen in this directory's `build.sh`.
- [build.sh](https://github.com/google/oss-fuzz/blob/master/projects/linkerd2/build.sh)
  is responsible for calling the fuzzing functions for each fuzzer in the
  linkerd2 project.
