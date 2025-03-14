---
date: 2019-08-22T13:59:53Z
title: "jx step boot upgrade"
slug: jx_step_boot_upgrade
url: /commands/jx_step_boot_upgrade/
---
## jx step boot upgrade

This step checks the version stream for updates to jenkins-x charts

### Synopsis

This step checks the version stream for updates to jenkins-x charts, by default the user is prompted to accept each update

```
jx step boot upgrade [flags]
```

### Examples

```
  # Checks the version stream for updates
  jx step boot upgrade
  
  # Checks the version stream for updates
  jx step boot upgrade --auto-upgrade
```

### Options

```
      --auto-upgrade       Auto apply upgrades
  -d, --dir string         the directory to look for the requirements file: jx-requirements.yml (default ".")
  -h, --help               help for upgrade
      --namespace string   the namespace that Jenkins X will be booted into. If not specified it defaults to $DEPLOY_NAMESPACE
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step boot](/commands/jx_step_boot/)	 - boot [command]

###### Auto generated by spf13/cobra on 22-Aug-2019
