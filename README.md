# parquet-format-rs

[![Build Status](https://travis-ci.org/sunchao/parquet-format-rs.svg?branch=master)](https://travis-ci.org/sunchao/parquet-format-rs)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![](http://meritbadge.herokuapp.com/parquet-format)](https://crates.io/crates/parquet-format)

Apache Parquet format for Rust, hosting the Thrift definition file and the generated .rs file.

## Updating Parquet format
- Update the `parquet.thrift` file
- Run `./generate_parquet_format.sh`
- Commit changes

Note that the version in `Cargo.toml` should match the Parquet format
version of the `parquet.thrift` in [apache/parquet-format](https://github.com/apache/parquet-format).
