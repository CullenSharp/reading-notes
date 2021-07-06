# Build Artifacts

![last seen](https://img.shields.io/github/last-commit/CullenSharp/reading-notes)

> Artifact: An artifact is something that is either produced or used by a project [(Apache Maven Project)](https://maven.apache.org/glossary.html)

[Build artifacts](https://www.jetbrains.com/help/teamcity/build-artifact.html) are files that get created at build-time. Think of package-lock.json, node_modules, logs, reports, packages, etc...

When deploying with `EC2` (Elastic Cloud Computing) with `Elastic Beanstalk` (henceforth referred to as EB), build artifacts are excluded. That's why we don't include the package-lock.json and node_modules. Those will be created at build time, and all `EB` needs are the instructions.

> So what's the difference between `build artifacts` and `dependencies`? Are they just two ways of referring to the same thing?

A dependency is something your project *relies* on. This could be libraries, modules, scripts, images, services. Dependencies are used at build time to determine what should be imported. For example, package.json holds all the information we need to tell our web application what dependencies it should include at build time.