---
date: 2019-08-22T13:59:53Z
title: "jx delete application"
slug: jx_delete_application
url: /commands/jx_delete_application/
---
## jx delete application

Deletes one or more applications from Jenkins

### Synopsis

Deletes one or more Applications 

Note that this command does not remove the underlying Git Repositories. 

For that see the https://jenkins-x.io/commands/jx_delete_repo/command.

```
jx delete application [flags]
```

### Examples

```
  # prompt for the available applications to delete
  jx delete application
  
  # delete a specific app
  jx delete application cheese
```

### Options

```
  -a, --all                             Selects all the matched applications
      --auto-merge                      Automatically merge GitOps pull requests that pass CI
  -f, --filter string                   Filter the list of applications to those containing this text
  -h, --help                            help for application
      --no-env                          Do not remove the application from any of the Environments
      --no-merge                        Disables automatic merge of promote Pull Requests
  -o, --org string                      github organisation/project name that source code resides in
      --pull-request-poll-time string   Poll time when waiting for a Pull Request to merge (default "20s")
  -t, --timeout string                  The timeout to wait for the promotion to succeed in the underlying Environment. The command fails if the timeout is exceeded or the promotion does not complete (default "1h")
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx delete](/commands/jx_delete/)	 - Deletes one or more resources

###### Auto generated by spf13/cobra on 22-Aug-2019
