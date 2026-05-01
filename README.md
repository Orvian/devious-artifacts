# Devious Artifacts

This repository serves as a Maven artifact repository for the Devious client project. It hosts published artifacts that are used as dependencies in the build process.

## Purpose

The devious-client project uses this repository to host:
- Deobfuscator JARs and POMs
- Other project dependencies that are not available in public Maven repositories

## Usage

Artifacts in this repository are referenced in `build.gradle.kts` files using:

```kotlin
repositories {
    maven {
        url = uri("https://raw.githubusercontent.com/Orvian/devious-artifacts/master")
    }
}
```

## Adding New Artifacts

To add a new artifact to this repository:

1. Build and publish the artifact to your local Maven repository:
   ```bash
   cd devious-client
   ./gradlew :module:publishToMavenLocal
   ```

2. Copy the artifact from `~/.m2/repository/` to this repository:
   ```bash
   cp -r ~/.m2/repository/path/to/artifact /path/to/devious-artifacts/
   ```

## Structure

The repository follows the standard Maven directory structure:
```
groupId/
  artifactId/
    version/
      artifactId-version.jar
      artifactId-version.pom
      artifactId-version.module
```

## Current Artifacts

- `net.unethicalite:deobfuscator` - Deobfuscation tool for RS client
- `com.openosrs:deobfuscator` - Alternative deobfuscator versions
