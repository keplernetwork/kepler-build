# Docker Image For Building Kepler

```
docker build -t keplerbuild:rust1.39 -f Dockerfile.build .
```

Go to kepler repo, and build into bash:

```
docker run -it --rm \
  -v $HOME/.cargo/registry/index:/usr/local/cargo/registry/index \
  -v $HOME/.cargo/registry/cache:/usr/local/cargo/registry/cache \
  -v $HOME/.cargo/git/db:/usr/local/cargo/git/db \
  -v `pwd`:/project \
  -w /project keplerbuild:rust1.39 bash
```

Inside the container run cargo build:

```
cargo build
```

### Cargo Caching Note

The following CARGO_HOME directories are recommended for caching:

- bin/
- registry/index/
- registry/cache/
- git/db/

But, cargo uses rustc in bin. If using MacOS, don't map that into the container.

See: https://doc.rust-lang.org/nightly/cargo/guide/cargo-home.html#caching-the-cargo-home-in-ci
