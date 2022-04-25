# parquet-format-rs

[![Build Status](https://travis-ci.org/sunchao/parquet-format-rs.svg?branch=master)](https://travis-ci.org/sunchao/parquet-format-rs)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![](http://meritbadge.herokuapp.com/parquet-format)](https://crates.io/crates/parquet-format)

Apache Parquet format for Rust, hosting the Thrift definition file and the generated .rs file.

## Usage and Versioning Policy

This crate previously tracked the Parquet format versions, which made keeping semver guarantees sometimes challenging.
As of version `3.0.0` of the crate, independent major versions are used whenever we update the Parquet format.

The below summarises the version mappings.

| parquet-format | parquet-format-rs |
| -------------- | ----------------- |
| 2.8.0          | 4.0.*             |
| 2.7.0          | 3.0.*             |
| 2.6.0          | 2.6.*             |
| 2.5.0          | 2.5.*             |
| 2.4.0          | 2.4.*             |


## Updating Parquet format

`parquet_format.rs` is built using thrift 0.13. There are backwards incompatible changes that prevent us from updating to a later thrift version. For that reason we use Docker to build thrift 0.13 and compile the rust code as described below.

```bash
git clone https://github.com/apache/thrift
cd thrift
git checkout v0.13.0
# docker build just builds a docker image with thrift dependencies
docker build -t thrift build/docker/ubuntu-bionic
# build/docker/scripts/cmake.sh actually compiles thrift
docker run -v $(pwd):/thrift/src -it thrift build/docker/scripts/cmake.sh && wget https://raw.githubusercontent.com/apache/parquet-format/apache-parquet-format-2.9.0/src/main/thrift/parquet.thrift && ./cmake_build/compiler/cpp/bin/thrift --gen rs parquet.thrift
```

Then copy the generated `parquet.rs` into `src/parquetformat.rs` and commit changes.

Note that the major version should be incremented when updating to a new Parquet format version.
