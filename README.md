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
| 2.4.0          | 2.4.*             |
| 2.5.0          | 2.5.*             |
| 2.6.0          | 2.6.*             |
| 2.7.0          | 3.0.*             |


## Updating Parquet format
- Update the `parquet.thrift` file
- Run `./generate_parquet_format.sh`
- Commit changes

Note that the major version should be incremented when updating to a new Parquet format version.
