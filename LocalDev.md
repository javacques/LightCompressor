# How to build and use lib locally

## Publish to local .m2

You can change the version of the lib in the `lightcompressor/build.gradle` in the `publishing` section.

Use the following command to publish lib to local .m2:
```shell
./gradlew clean publishToMavenLocal
```

Note: If you run into problems executing `./gradlew`, you should probably make it executable first.

## Use local lib in your project

Comment out or delete `maven { url 'https://jitpack.io' }` in your project-level `build.gradle`.

Use `mavenLocal()` instead:
```groovy
allprojects {
    repositories {
        ...
        mavenLocal()
    }
}
```

Add dependency itself to your apps dependencies:
```groovy
dependencies {
    ...
    implementation 'com.github.AbedElazizShe:LightCompressor:1.2.3-my-hotfix'
}
```
