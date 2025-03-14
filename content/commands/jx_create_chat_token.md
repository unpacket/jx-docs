---
date: 2019-08-22T13:59:53Z
title: "jx create chat token"
slug: jx_create_chat_token
url: /commands/jx_create_chat_token/
---
## jx create chat token

Adds a new token/login for a user on a Chat service server

### Synopsis

Creates a new User Token for a Chat service

```
jx create chat token [username] [flags]
```

### Examples

```
  # Add a new User Token for a Chat service
  jx create chat token -n jira someUserName
  
  # As above with the password being passed in
  jx create git token -n jira -p somePassword someUserName
```

### Options

```
  -t, --api-token string   The API Token for the user
  -h, --help               help for token
  -n, --name string        The name of the Git server to add a user
      --timeout string     The timeout if using browser automation to generate the API token (by passing username and password)
  -u, --url string         The URL of the Git server to add a user
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx create chat](/commands/jx_create_chat/)	 - Creates a chat server resource

###### Auto generated by spf13/cobra on 22-Aug-2019
