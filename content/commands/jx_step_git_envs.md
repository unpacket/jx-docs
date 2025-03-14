---
date: 2019-08-22T13:59:53Z
title: "jx step git envs"
slug: jx_step_git_envs
url: /commands/jx_step_git_envs/
---
## jx step git envs

Creates the Git environment variables for the current pipeline Git credentials

### Synopsis

This pipeline step generates a Git environment variables from the current Git provider pipeline Secrets

```
jx step git envs [flags]
```

### Examples

```
  # Sets the Git environment variables for the current GitHub provider
  jx step git envs
  
  # Sets the Gie environment variables for the current Gtilab provider
  jx step git envs --service-kind=gitlab
```

### Options

```
  -h, --help                  help for envs
      --service-kind string   The kind of git service (default "github")
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step git](/commands/jx_step_git/)	 - git [command]

###### Auto generated by spf13/cobra on 22-Aug-2019
