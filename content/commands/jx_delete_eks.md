---
date: 2019-08-22T13:59:53Z
title: "jx delete eks"
slug: jx_delete_eks
url: /commands/jx_delete_eks/
---
## jx delete eks

Deletes EKS cluster.

### Synopsis

Deletes EKS cluster resource. Under the hood this command delegated removal operation to eksctl.

```
jx delete eks [flags]
```

### Examples

```
  # Delete EKS cluster
  jx delete eks
```

### Options

```
  -h, --help             help for eks
  -o, --output string    The output format such as 'yaml'
      --profile string   AWS profile to use.
      --region string    AWS region to use. Default: us-west-2
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx delete](/commands/jx_delete/)	 - Deletes one or more resources

###### Auto generated by spf13/cobra on 22-Aug-2019
