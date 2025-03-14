---
date: 2019-08-22T13:59:53Z
title: "jx create domain gke"
slug: jx_create_domain_gke
url: /commands/jx_create_domain_gke/
---
## jx create domain gke

Create a managed domain for GKE

### Synopsis

Create a Domain in GCP so it can be used with GKE

```
jx create domain gke [flags]
```

### Examples

```
  # Create the Domain in Google Cloud
  jx create domain gke -d foo.bar.io
```

### Options

```
  -d, --domain string       The Domain you wish to be managed
  -h, --help                help for gke
  -p, --project-id string   Override the current Project ID
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx create domain](/commands/jx_create_domain/)	 - Create a domain in a managed DNS service provider

###### Auto generated by spf13/cobra on 22-Aug-2019
