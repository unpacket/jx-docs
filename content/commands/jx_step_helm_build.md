---
date: 2019-08-22T13:59:53Z
title: "jx step helm build"
slug: jx_step_helm_build
url: /commands/jx_step_helm_build/
---
## jx step helm build

Builds the helm chart in a given directory and validate the build completes

### Synopsis

Builds the helm chart in a given directory. 

This step is usually used to validate any GitOps Pull Requests.

```
jx step helm build [flags]
```

### Examples

```
  # builds the helm chart in the env directory
  jx step helm build --dir env
```

### Options

```
      --boot                          In Boot mode we load the Version Stream from the 'jx-requirements.yml' and use that to replace any missing versions in the 'reuqirements.yaml' file from the Version Stream
      --clone-https git@foo/bar.git   Clone the environment Git repo over https rather than ssh which uses git@foo/bar.git (default true)
  -d, --dir string                    The directory containing the helm chart to apply (default ".")
      --git-provider string           The Git provider for the environment Git repository (default "github.com")
  -h, --help                          help for build
      --provider-values-dir string    The optional directory of kubernetes provider specific override values.tmpl.yaml files a kubernetes provider specific folder
  -r, --recursive                     Build recursively the dependent charts
      --remote                        If enabled assume we are in a remote cluster such as a stand alone Staging/Production cluster
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step helm](/commands/jx_step_helm/)	 - helm [command]

###### Auto generated by spf13/cobra on 22-Aug-2019
