---
date: 2019-08-22T13:59:53Z
title: "jx step tag"
slug: jx_step_tag
url: /commands/jx_step_tag/
---
## jx step tag

Creates a git tag and pushes to remote repo

### Synopsis

This pipeline step command creates a git tag using a version number prefixed with 'v' and pushes it to a remote origin repo. 

This commands effectively runs: 

  $ git commit -a -m "release $(VERSION)" --allow-empty
  $ git tag -fa v$(VERSION) -m "Release version $(VERSION)"
  $ git push origin v$(VERSION)

```
jx step tag [flags]
```

### Examples

```
  jx step tag --version 1.0.0
```

### Options

```
  -d, --charts-dir string                the directory of the chart to update the version
  -r, --charts-value-repository string   the fully qualified image name without the version tag. e.g. 'dockerregistry/myorg/myapp'
      --dir string                       the directory which may contain a 'jenkins-x.yml'
  -h, --help                             help for tag
      --no-apply                         Do not push the tag to the server, this is used for example in dry runs
  -v, --version string                   version number for the tag [required]
      --version-file string              The file name used to load the version number from if no '--version' option is specified (default "VERSION")
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step](/commands/jx_step/)	 - pipeline steps

###### Auto generated by spf13/cobra on 22-Aug-2019
