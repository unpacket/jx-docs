---
date: 2019-08-22T13:59:53Z
title: "jx step create pullrequest make"
slug: jx_step_create_pullrequest_make
url: /commands/jx_step_create_pullrequest_make/
---
## jx step create pullrequest make

Creates a Pull Request on a git repository, doing an update to a Makefile

### Synopsis

Creates a Pull Request updating a Makefile so that any variables defined as <name>:= <value>will have the value replaced with the new version 

Files named Makefile or Makefile. * will be updated

```
jx step create pullrequest make [flags]
```

### Examples

```
  jx step create pr make --name CHART_VERSION --version 1.2.3 --repo https://github.com/jenkins-x/cloud-environments.git
```

### Options

```
      --base string        The branch to create the pull request into (default "master")
      --branch string      Branch to clone and generate a pull request from (default "master")
      --component string   The component of the git repo which caused this change; useful if you have a complex or monorepo setup and want to differentiate between different components from the same repo
      --dry-run            Perform a dry run, the change will be generated and committed, but not pushed or have a PR created
  -h, --help               help for make
      --name string        The name of the variable to use when doing updates
  -r, --repo stringArray   Git repo update
      --src-repo string    The git repo which caused this change; if this is a dependency update this will cause commit messages to be generated which can be parsed by jx step changelog. By default this will be read from the environment variable REPO_URL
  -v, --version string     The version to change. If no version is supplied the latest version is found
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step create pullrequest](/commands/jx_step_create_pullrequest/)	 - create pullrequest [command]

###### Auto generated by spf13/cobra on 22-Aug-2019
