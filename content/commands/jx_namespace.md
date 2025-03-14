---
date: 2019-08-22T13:59:53Z
title: "jx namespace"
slug: jx_namespace
url: /commands/jx_namespace/
---
## jx namespace

View or change the current namespace context in the current Kubernetes cluster

### Synopsis

Displays or changes the current namespace.

```
jx namespace [flags]
```

### Examples

```
  # view the current namespace
  jx --batch-mode ns
  
  # interactively select the namespace to switch to
  jx ns
  
  # change the current namespace to 'cheese'
  jx ns cheese
  
  # change the current namespace to 'brie' creating it if necessary
  jx ns --create brie
```

### Options

```
  -c, --create   Creates the specified namespace if it does not exist
  -h, --help     help for namespace
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx](/commands/jx/)	 - jx is a command line tool for working with Jenkins X

###### Auto generated by spf13/cobra on 22-Aug-2019
