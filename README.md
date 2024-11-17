# zsqlite-c

Add SQLite C as a static library into your build.

## Install

Add as a dependency:

```sh
zig fetch --save "https://github.com/thiago-negri/zsqlite-c/archive/refs/tags/v3.47.0.zip"
```

Add to your build:

```zig
// Add SQLite C as a static library.
const zsqlite_c = b.dependency("zsqlite-c", .{ .target = target, .optimize = optimize });
const zsqlite_c_artifact = zsqlite_c.artifact("zsqlite-c");
lib.linkLibrary(zsqlite_c_artifact);
```

## Use

```zig
const c = @cImport({
    @include("sqlite3.h");
});
```
