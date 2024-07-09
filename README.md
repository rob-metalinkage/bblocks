# Building Blocks

Bootstrap page containing an overview of building blocks and a building blocks register.

[See it live here](https://blocks.ogc.org/)

## Validation Reports
[Summary](https://opengeospatial.github.io/bblocks/tests/report.html)

## Local build/test

You need a functioning Docker environment to build the Building Blocks Register locally. 
All the output files will be generated under `build-local`.

1. Clone the repository: `git clone https://github.com/opengeospatial/bblocks.git --recurse-submodules`
2. Change into the repository folder: `cd bblocks` 
3. Update submodules: `git submodule update --recursive --remote`
4. Build the Register: run build.sh or
   ```shell
   # Process building blocks
   docker run --pull=always --rm --workdir /workspace -v "$(pwd):/workspace" --user $(id -u) \
      ghcr.io/opengeospatial/bblocks-postprocess  --clean true \
      --items-dir registereditems/ \
      --base-url https://opengeospatial.github.io/bblocks/
    ```

docker run --pull=always --rm --workdir /workspace -v $(pwd):/workspace --user $UID       ghcr.io/opengeospatial/bblocks-postprocess  --clean true    --items-dir registereditems/      --base-url https://opengeospatial.github.io/bblocks/

If you need to rebuild the Register, just run steps 2 and 3.

## License

This code is released under [Apache 2.0](./LICENSE) license.

## Contributing

Please refer to [CONTRIBUTING.md](CONTRIBUTING.md).
