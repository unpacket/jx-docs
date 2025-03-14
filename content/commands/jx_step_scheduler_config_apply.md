---
date: 2019-08-22T13:59:53Z
title: "jx step scheduler config apply"
slug: jx_step_scheduler_config_apply
url: /commands/jx_step_scheduler_config_apply/
---
## jx step scheduler config apply

scheduler config apply

### Synopsis

This command will transform your pipeline schedulers in to prow config. If you are using gitops the prow config will be added to your environment repository. For non-gitops environments the prow config maps will applied to your dev environment.

```
jx step scheduler config apply [flags]
```

### Examples

```
  jx step scheduler config apply
```

### Options

```
      --agent string   The scheduler agent to use e.g. Prow (default "prow")
      --direct         Skip generating a PR and apply the pipeline config directly to the cluster when using gitops mode.
  -h, --help           help for apply
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step scheduler config](/commands/jx_step_scheduler_config/)	 - scheduler config [command]

###### Auto generated by spf13/cobra on 22-Aug-2019
