---
date: 2019-08-22T13:59:53Z
title: "jx shell"
slug: jx_shell
url: /commands/jx_shell/
---
## jx shell

Create a sub shell so that changes to the Kubernetes context, namespace or environment remain local to the shell

### Synopsis

Create a sub shell so that changes to the Kubernetes context, namespace or environment remain local to the shell.

```
jx shell [flags]
```

### Examples

```
  # create a new shell where the context changes are local to the shell only
  jx shell
  
  # create a new shell using a specific named context
  jx shell prod-cluster
  
  # ends the current shell and returns to the previous Kubernetes context
  exit
```

### Options

```
  -f, --filter string   Filter the list of contexts to switch between using the given text
  -h, --help            help for shell
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx](/commands/jx/)	 - jx is a command line tool for working with Jenkins X

###### Auto generated by spf13/cobra on 22-Aug-2019
