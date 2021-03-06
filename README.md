![LDBC_LOGO](https://raw.githubusercontent.com/wiki/ldbc/ldbc_snb_datagen/images/ldbc-logo.png)
# LDBC SNB Documentation

[![Build Status](https://travis-ci.org/ldbc/ldbc_snb_docs.svg?branch=master)](https://travis-ci.org/ldbc/ldbc_snb_docs)

[[latest stable build (PDF)]](http://ldbc.github.io/ldbc_snb_docs/ldbc-snb-specification.pdf) [[latest snapshot build (PDF)]](http://ldbc.github.io/ldbc_snb_docs_snapshot/ldbc-snb-specification.pdf)

## Query specifications

The query specifications are defined in [YAML](http://yaml.org/) format.

Results are categorized according to their source of origin:

* **raw** (`R`), if the result is returned with an unmodified value and type. This is the default category.
* **calculated** (`C`), if the result is calculated from other values and conditions.
* **aggregated** (`A`), if the result is an aggregated value, e.g. a _count_ or a _sum_ of another value. If a result is both calculated and aggregated (e.g. `count(x) + count(y)` or `avg(x + y)`), it is considered an aggregated result.

### Generating query cards

1. Install the following dependencies:

    * Python3:

       ```
       sudo apt-get install -y python3 python3-pip python3-setuptools
       ```

    * Pandoc:

       ```
       sudo apt-get install -y pandoc
       ```

1. To generate the TeX files for query cards, run the following command:

    ```
    ./generate-tex.py
    ```

## Building the document

To build the document, run `make` or `make texfot`. The latter requires Perl but gives you a cleaner output.

If you are using a Linux-based system, you can also check the [`.travis.yml`](.travis.yml) file as it provides a precise documentation of what you should do in order to build the docs.

## Naming conventions

* if the attribute exists in the graph as part of an entity (vertex/edge) and is returned unchanged, name it `entity.attributeName`
* if it is computed or aggregated, use `camelCase` notation
