---
date: 2019-08-22T13:59:53Z
title: "jx create etc-hosts"
slug: jx_create_etc-hosts
url: /commands/jx_create_etc-hosts/
---
## jx create etc-hosts

Creates a new Git server URL

### Synopsis

Creates /etc/hosts entries for all current exposed services

```
jx create etc-hosts kind [url] [flags]
```

### Examples

```
  # Creates /etc/hosts entries for all current exposed services
  sudo jx create etc-hosts
```

### Options

```
  -h, --help          help for etc-hosts
  -i, --ip string     The IP address of the node to point the host entries to
  -n, --name string   The etc hosts file to edit (default "/etc/hosts")
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx create](/commands/jx_create/)	 - Create a new resource

###### Auto generated by spf13/cobra on 22-Aug-2019
