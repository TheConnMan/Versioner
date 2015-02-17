Versioner
=========

Git versioning and tagging without the hassle.

## Description

**Versioner** helps automate version bumping and tagging in Git applications. Once you have set up your local Git config to point to the location of the application version tagging is easy. **Versioner** will automatically:

- Bump the version number
- Commit the changes
- Merge them into master
- Tag the version
- Switch back to the development branch

## Requirements

- Bash
- Git

## Installing

To install download the [latest version](https://github.com/TheConnMan/Versioner/archive/master.zip) and extract `versioner` into a permanant location. You can also move `versioner` to a location in your path for convenience.

### Local Config Setup

Before using **versioner** you'll need to set a few configs within your local git repository. You can use the **Setup Wizard** or **Default Setup** below to get started. Additional info about the setup items is also below.

#### Setup Wizard

There is a setup wizard to help with initial setup. Run `versioner -w` to use this wizard.

#### Default Setup

There is an option to set up and default config if the project is a **Grails** project. Run `versioner -s grails` to use this default setup.

##### Branch

The development branch is the branch where the version will be incremented and committed. This branch will then be merged into master and switched back to after completion.

##### File

You'll also need to set the file which contains your application version number. This file path must be a relative path from the root of the project to the file.

##### Context

To find and replace the version number within the file above a little context is needed. Set the **context** to the contents of the line containing the version number in the file above. For example, the following file would use the context [**app.version=**].

```
#Grails Metadata file
#Sun Jan 1 13:15:17 EST 2014
app.grails.version=2.3.0
app.name=myapp
app.servlet.version=3.0
app.version=1.1.2
```

## Use

To increment the version of an app run **versioner** in the root directory of your git repository with the following options:

Usage: `versioner [-v version] [-t tag message] [-s setup] [-Mmbwh]`
- -v: version number
- -t: tag message
- -s: setup type (grails)
- -M: Major version bump
- -m: Minor version bump
- -b: Build version bump
- -w: Setup wizard
- -h: help

### Versions

**Versioner** allows you to specify a specific version using the `-v` option, or specify and **Major** (`-M`), **Minor** (`-m`), or **Build** (`-b`) level bump. Any of these three flags will auto-increment that build level and set and lower levels to zero (e.g. **1.1.1** -> **2.0.0**).

## Support

Please use [GitHub Issues](https://github.com/TheConnMan/Versioner.git) to recommend additions or report bugs.

## License

MIT