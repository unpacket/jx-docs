---
date: 2019-08-22T13:59:53Z
title: "jx create jhipster"
slug: jx_create_jhipster
url: /commands/jx_create_jhipster/
---
## jx create jhipster

Create a new JHipster based application and import the generated code into Git and Jenkins for CI/CD

### Synopsis

Creates a new JHipster application and then optionally setups CI/CD pipelines and GitOps promotion.
  
      JHipster is an application generator for gRPC services in Go with a set of tools/libraries.
  
      This command is expected to be run within your '$GOHOME' directory. e.g. at '$GOHOME/src/github.com/myOrgOrUser/'
  
      For more documentation about JHipster see: [https://www.jhipster.tech/](https://www.jhipster.tech/)
  
See Also: 

  * jx create project : https://jenkins-x.io/commands/jx_create_project

```
jx create jhipster [flags]
```

### Examples

```
  # Create a JHipster application and be prompted for the folder name
  jx create jhipster
  
  # Create a JHipster application in the myname sub-folder folder
  jx create jhipster myname
```

### Options

```
      --branches string                The branch pattern for branches to trigger CI/CD pipelines on
      --credentials string             The Jenkins credentials name used by the job
      --deploy-kind string             The kind of deployment to use for the project. Should be one of knative, default
      --disable-updatebot              disable updatebot-maven-plugin from attempting to fix/update the maven pom.xml
      --docker-registry-org string     The name of the docker registry organisation to use. If not specified then the Git provider organisation will be used
      --dry-run                        Performs local changes to the repo but skips the import into Jenkins X
      --external-jenkins-url string    The jenkins url that an external git provider needs to use
      --git-api-token string           The Git API token to use for creating new Git repositories
      --git-private                    Create new Git repositories as private
      --git-provider-kind string       Kind of Git server. If not specified, kind of server will be autodetected from Git provider URL. Possible values: bitbucketcloud, bitbucketserver, gitea, gitlab, github, fakegit
      --git-provider-url string        The Git server URL to create new Git repositories inside (default "https://github.com")
      --git-username string            The Git username to use for creating new Git repositories
  -h, --help                           help for jhipster
      --import-commit-message string   Specifies the initial commit message used when importing the project
  -m, --import-mode string             The import mode to use. Should be one of Jenkinsfile, YAML
      --jenkinsfile string             The name of the Jenkinsfile to use. If not specified then 'Jenkinsfile' will be used
      --list-packs                     list available draft packs
      --name string                    Specify the Git repository name to import the project into (if it is not already in one)
      --no-draft                       Disable Draft from trying to default a Dockerfile and Helm Chart
      --no-import                      Disable import after the creation
      --no-jenkinsfile                 Disable defaulting a Jenkinsfile if its missing
      --org string                     Specify the Git provider organisation to import the project into (if it is not already in one)
  -o, --output-dir string              Directory to output the project to. Defaults to the current directory
      --pack string                    The name of the pack to use
      --scheduler string               The name of the Scheduler configuration to use for ChatOps when using Prow
      --use-default-git                use default git account
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx create](/commands/jx_create/)	 - Create a new resource

###### Auto generated by spf13/cobra on 22-Aug-2019
