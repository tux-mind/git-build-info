# git-build-info
Gradle plugin to incorporate Git repo info into your build

[![Build Status](https://travis-ci.org/madvay/git-build-info.svg?branch=master)](https://travis-ci.org/madvay/git-build-info)

## Usage
In the build.gradle file:

```gradle
plugins {
    id "com.madvay.tools.build.gitbuildinfo" version "0.1.5-alpha"
}

buildStamp {
    // The git commit SHA will be appended to this url to generate the final url.
    repoBaseUrl "https://github.com/USER/REPO/tree/"
    // BuildInfo.java will be added under this package, in a
    // generated build/ directory.
    packageName "com.example"
}
```

This plugin eats its own dogfood, so look at [build.gradle](build.gradle) to
see how we use it.

## Sample BuildInfo.java
Most of the variables added are straightforward.
`GIT_IS_CLEAN` is true iff you have no changes in your git working directory (or
your git index).  This means the state of the code can be fully specified by the
`GIT_COMMIT` in your local repository.

```java

// This is an auto-generated file.  Do not edit.
// Generated using: https://github.com/madvay/git-build-info

package com.madvay.tools.build.gitbuildinfo;

public class BuildInfo {
    public static final String VERSION = "0.0.7-alpha-SNAPSHOT";
    public static final String GIT_COMMIT = "ea9f50061005f58811c5846089c4e7a26e3cdd29";
    public static final String URL = "https://github.com/madvay/source/git-build-info/tree/ea9f50061005f58811c5846089c4e7a26e3cdd29";
    public static final String TIMESTAMP = "20150823T225946+0000";
    public static final boolean GIT_IS_CLEAN = false;
}
```

## License
See [LICENSE](LICENSE) and [NOTICE](NOTICE).
