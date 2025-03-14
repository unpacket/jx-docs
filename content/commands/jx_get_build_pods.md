---
date: 2019-08-22T13:59:53Z
title: "jx get build pods"
slug: jx_get_build_pods
url: /commands/jx_get_build_pods/
---
## jx get build pods

Displays the build pods and their details

### Synopsis

Display the knative build pods

```
jx get build pods [flags]
```

### Examples

```
  # List all the knative build pods
  jx get build pods
  
  # List all the pending knative build pods
  jx get build pods -p
  
  # List all the knative build pods for a given repository
  jx get build pods --repo cheese
  
  # List all the pending knative build pods for a given repository
  jx get build pods --repo cheese -p
  
  # List all the knative build pods for a given Pull Request
  jx get build pods --repo cheese --branch PR-1234
```

### Options

```
      --branch string      Filters the branch
      --build string       Filter a specific build number
      --context string     Filters the context of the build
  -f, --filter string      Filters the build name by the given text
  -h, --help               help for pods
  -n, --namespace string   The namespace to look for the build pods. Defaults to the current namespace
  -o, --owner string       Filters the owner (person/organisation) of the repository
  -p, --pending            Filter builds which are currently pending or running
  -r, --repo string        Filters the build repository
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx get build](/commands/jx_get_build/)	 - Display one or more build resources

###### Auto generated by spf13/cobra on 22-Aug-2019
