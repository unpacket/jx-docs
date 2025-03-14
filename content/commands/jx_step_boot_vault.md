---
date: 2019-08-22T13:59:53Z
title: "jx step boot vault"
slug: jx_step_boot_vault
url: /commands/jx_step_boot_vault/
---
## jx step boot vault

This step boots up Vault in the current cluster if its enabled in the 'jx-requirements.yml' file and is not already installed

### Synopsis

This step boots up Vault in the current cluster if its enabled in the 'jx-requirements.yml' file and is not already installed. 

This step is intended to be used in the Jenkins X Boot Pipeline: https://jenkins-x.io/getting-started/boot/

```
jx step boot vault [flags]
```

### Examples

```
  # boots up Vault if its required
  jx step boot vault
```

### Options

```
  -d, --dir string         the directory to look for the requirements file: jx-requirements.yml (default ".")
  -h, --help               help for vault
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
