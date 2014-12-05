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

Before using **versioner** you'll need to set a few configs within your local git repository.

#### Branch

The development branch is the branch where the version will be incremented and committed. This branch will then be merged into master and switched back to after completion. To set this branch run the following:

```
git config --local --add versioner.branch [branch]
```

Replace **[branch]** with the name of your development branch.

#### File

You'll also need to set the file which contains your application version number. This file path must be a relative path from the root of the project to the file. Set this by running the following:

```
git config --local --add versioner.file [file]
```

Replace **[file]** with the relative path of your file.

#### Context

To find and replace the version number within the file above a little context is needed. Set the **context** to the contents of the line containing the version number in the file above. For example, the following file would use the context [**app.version=**].

```
#Grails Metadata file
#Sun Jan 1 13:15:17 EST 2014
app.grails.version=2.3.0
app.name=myapp
app.servlet.version=3.0
app.version=1.1.2
```

Set the context by running the following:

```
git config --local --add versioner.context [context]
```

Replace **[context]** with the version number context.

## Use

To increment the version of an app run **versioner** in the root directory of your git repository with the following options:

Usage: `versioner [-v version] [-m message]`
- -v: version number
- -m: tag message
- -h: help

## Support

Please use [GitHub Issues](https://github.com/TheConnMan/Versioner.git) to recommend additions or report bugs.

## License

MIT