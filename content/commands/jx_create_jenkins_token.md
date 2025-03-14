---
date: 2019-08-22T13:59:53Z
title: "jx create jenkins token"
slug: jx_create_jenkins_token
url: /commands/jx_create_jenkins_token/
---
## jx create jenkins token

Adds a new username and API token for a Jenkins server

### Synopsis

Creates a new user and API Token for the current Jenkins server

```
jx create jenkins token [username] [flags]
```

### Examples

```
  # Add a new API Token for a user for the current Jenkins server
  # prompting the user to find and enter the API Token
  jx create jenkins token someUserName
  
  # Add a new API Token for a user for the current Jenkins server
  # using browser automation to login to the Git server
  # with the username an password to find the API Token
  jx create jenkins token -p somePassword someUserName
```

### Options

```
  -t, --api-token string          The API Token for the user
  -m, --custom                    Use a custom Jenkins App instead of the default execution engine in Jenkins X
      --health-timeout duration   The maximum duration to wait for the Jenkins service to be healthy before trying to create the API token (default 30m0s)
  -h, --help                      help for token
  -j, --jenkins-name string       The name of the custom Jenkins App if you don't wish to use the default execution engine in Jenkins X
  -n, --name string               The name of the Git server to add a user
      --namespace string          The namespace of the secret where the Jenkins API token will be stored
      --no-rest                   Disables the use of REST calls to automatically find the API token if the user and password are known
  -p, --password string           The User password to try automatically create a new API Token
      --recreate-token            Should we recreate the API token if it already exists
      --timeout string            The timeout if using REST to generate the API token (by passing username and password)
  -u, --url string                The URL of the Git server to add a user
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx create jenkins](/commands/jx_create_jenkins/)	 - Creates a Jenkins resource

###### Auto generated by spf13/cobra on 22-Aug-2019
