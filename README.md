# openssl-win-x64

The static OpenSSL libraries [Valk](https://valk-lang.dev) links when cross compiling for Windows x64.
A Valk release ships OpenSSL for its own platform only; a program that targets `win-x64` from another
system and uses `valk.crypto` or TLS (`net.Ssl`, `https`) adds this package as a dependency.
Programs without crypto or TLS cross compile without it.

Requires Valk 0.8.0 or newer.

## Install

```
vman install github.com/valk-lang/openssl-win-x64
valk build ./src --target win-x64
```

The package has no code: it holds `libs/win-x64/` with `libcrypto` and `libssl`, which the compiler
finds through the dependency. Nothing has to be imported.

## Contents

OpenSSL 3.5.9 (LTS, supported until April 2030), built from the official release tarball with
`misc/openssl/build.sh` in the [valk](https://github.com/valk-lang/valk) repository: static libraries,
no loadable modules, no legacy algorithms, the same options for every platform.
