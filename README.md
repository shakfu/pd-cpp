# puredata externals in cpp


## Requirements


Quickstart: see the [helloworld](helloworld) project for a very minimal example.

To compile a puredata external with c++ on macOS Catalina:

1. Use [pd-lib-builder](https://github.com/pure-data/pd-lib-builder) 

2. Wrap `<name>_setup` function with `extern "C" { <name_setup }`

3. `class_new` call in `<name>_setup` should terminate with `A_NULL` instead of `0`.

4. In the project `Makefile`, for macOS Catalina at least, add the following to `cflags`:

```bash

cflags += -stdlib=libc++ -mmacosx-version-min=10.9

```

## Credits


- ref: <https://lists.puredata.info/pipermail/pd-list//2018-06/122775.html>
