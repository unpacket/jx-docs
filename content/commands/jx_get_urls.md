---
date: 2019-08-22T13:59:53Z
title: "jx get urls"
slug: jx_get_urls
url: /commands/jx_get_urls/
---
## jx get urls

Display one or more URLs

### Synopsis

Display one or more URLs from the running services.

```
jx get urls [flags]
```

### Examples

```
  # List all URLs in this namespace
  jx get url
```

### Options

```
  -e, --env string         Specifies the Environment name to look inside
  -h, --help               help for urls
      --host               Only displays host names of the URLs and does not open the browser
  -n, --namespace string   Specifies the namespace name to look inside
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx get](/commands/jx_get/)	 - Display one or more resources

###### Auto generated by spf13/cobra on 22-Aug-2019
