---
date: 2019-08-22T13:59:53Z
title: "jx get branchpattern"
slug: jx_get_branchpattern
url: /commands/jx_get_branchpattern/
---
## jx get branchpattern

Display the git branch patterns for the current Team used on creating and importing projects

### Synopsis

Display the git branch patterns for the current Team used on creating and importing projects 

For more documentation see: https://jenkins-x.io/developing/import/#branch-patterns

```
jx get branchpattern [flags]
```

### Examples

```
  # List the git branch patterns for the current team
  jx get branchpattern
```

### Options

```
  -h, --help            help for branchpattern
  -o, --output string   The output format such as 'yaml'
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx get](/commands/jx_get/)	 - Display one or more resources

###### Auto generated by spf13/cobra on 22-Aug-2019
