# shazam-signature-jni
Shazam audio fingerprinting signature generator as JNI library.

The implementation is extracted from [SongRec](https://github.com/marin-m/SongRec) by [@marin-m](https://github.com/marin-m). All of the research credit goes to them. The original project page provides details about the algorithm & its working.

## Build

1. Clone the repository.

```
git clone https://github.com/alexmercerind/shazam-signature-jni.git
cd shazam-signature-generator
```

2. Create `.cargo/config` to specify the Android NDK location. e.g.

```
[target.aarch64-linux-android]
ar = "$(ANDROID_NDK)/bin/llvm-ar"
linker = "$(ANDROID_NDK)/bin/aarch64-linux-android21-clang"

[target.armv7-linux-androideabi]
ar = "$(ANDROID_NDK)/bin/llvm-ar"
linker = "$(ANDROID_NDK)/bin/armv7a-linux-androideabi21-clang"

[target.i686-linux-android]
ar = "$(ANDROID_NDK)/bin/llvm-ar"
linker = "$(ANDROID_NDK)/bin/i686-linux-android21-clang"

[target.x86_64-linux-android]
ar = "$(ANDROID_NDK)/bin/llvm-ar"
linker = "$(ANDROID_NDK)/bin/x86_64-linux-android21-clang"
```

3. Add Android targets for Rust.

```
rustup target add armv7-linux-androideabi
rustup target add i686-linux-android
rustup target add aarch64-linux-android
rustup target add x86_64-linux-android
```

4. Build for each target.

```
cargo build --target TARGET --release
```


## Legal

This software is released under the [GNU GPL v3](https://www.gnu.org/licenses/gpl-3.0.html) license. Please note that in certain countries located outside of the European Union, especially the United States, software patents may apply.
