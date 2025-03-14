---
date: 2019-08-22T13:59:53Z
title: "jx step create pullrequest regex"
slug: jx_step_create_pullrequest_regex
url: /commands/jx_step_create_pullrequest_regex/
---
## jx step create pullrequest regex

Creates a Pull Request on a git repository, doing an update using the provided regex

### Synopsis

Creates a Pull Request on a git repository updating files using a regex.
  
      Any named capturing group called "version" will be replaced. If there are no named capturing groups, then the
      all the capturing group will be used.
  
"

```
jx step create pullrequest regex [flags]
```

### Examples

```
  # Create a PR to change the value of release = <value> to $VERSION in the config.toml file
  ./build/linux/jx step create pr regex --regex "\s*release = \"(.*)\"" --version $VERSION --files config.toml \
  --repo https://github.com/jenkins-x/jx-docs.git
  
  # Create a PR to change the value of the ImageTag: <value> to ${VERSION} where the previous line is Image:
  # "jenkinsxio/jenkinsx" in the jenkins-x-platform/values.yaml file
  jx step create pr regex --regex "^(?m)\s+Image: \"jenkinsxio\/jenkinsx\"\s+ImageTag: \"(.*)\"$" \
  --version ${VERSION} --files values.yaml --repo https://github.com/jenkins-x/jenkins-x-platform.git
  
  # Create a PR to change the value of the named capture to $VERSION in the config.toml file
  ./build/linux/jx step create pr regex --regex "\s*release = \"(?P<version>.*)\"" --version $VERSION --files config.toml \
  --repo https://github.com/jenkins-x/jx-docs.git
```

### Options

```
      --base string         The branch to create the pull request into (default "master")
      --branch string       Branch to clone and generate a pull request from (default "master")
      --component string    The component of the git repo which caused this change; useful if you have a complex or monorepo setup and want to differentiate between different components from the same repo
      --dry-run             Perform a dry run, the change will be generated and committed, but not pushed or have a PR created
      --files stringArray   A glob describing the files to change
  -h, --help                help for regex
      --regex string        The regex to use when doing updates
  -r, --repo stringArray    Git repo update
      --src-repo string     The git repo which caused this change; if this is a dependency update this will cause commit messages to be generated which can be parsed by jx step changelog. By default this will be read from the environment variable REPO_URL
  -v, --version string      The version to change. If no version is supplied the latest version is found
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step create pullrequest](/commands/jx_step_create_pullrequest/)	 - create pullrequest [command]

###### Auto generated by spf13/cobra on 22-Aug-2019
