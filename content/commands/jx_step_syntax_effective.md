---
date: 2019-08-22T13:59:53Z
title: "jx step syntax effective"
slug: jx_step_syntax_effective
url: /commands/jx_step_syntax_effective/
---
## jx step syntax effective

Outputs an effective representation of the pipeline to be executed

### Synopsis

Reads the appropriate jenkins-x.yml, depending on context, from the current directory, if one exists, and outputs an effective representation of the pipelines

```
jx step syntax effective [flags]
```

### Examples

```
  # view the effective pipeline
  jx step syntax effective
  
  # view the short version of the effective pipeline
  jx step syntax effective -s
```

### Options

```
  -c, --context string               The pipeline context if there are multiple separate pipelines for a given branch
      --default-image string         Specify the docker image to use if there is no image specified for a step and there's no Pod Template (default "maven")
      --docker-registry string       The Docker Registry host name to use which is added as a prefix to docker images
      --docker-registry-org string   The Docker registry organisation. If blank the git repository owner is used
  -e, --env stringArray              List of custom environment variables to be applied to resources that are created
  -h, --help                         help for effective
      --image string                 Specify a custom image to use for the steps which overrides the image in the PodTemplates
      --kaniko-image string          The docker image for Kaniko (default "gcr.io/kaniko-project/executor:9912ccbf8d22bbafbf971124600fbb0b13b9cbd6")
      --output-dir string            The directory to write the output to as YAML. Defaults to STDOUT if neither --output-dir nor --output-file is specified.
      --output-file string           The file to write the output to as YAML. If unspecified and --output-dir is specified, the filename defaults to 'jenkins-x[-context]-effective.yml'
  -p, --pack string                  The build pack name. If none is specified its discovered from the source code
      --project-id string            The cloud project ID. If not specified we default to the install project
  -r, --ref string                   The Git reference (branch,tag,sha) in the Git repository to use
      --service-account string       The Kubernetes ServiceAccount to use to run the pipeline (default "tekton-bot")
  -s, --short                        Use short concise output
      --source string                The name of the source repository (default "source")
  -u, --url string                   The URL for the build pack Git repository
      --use-kaniko                   Enables using kaniko directly for building docker images (default true)
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step syntax](/commands/jx_step_syntax/)	 - syntax [command]

###### Auto generated by spf13/cobra on 22-Aug-2019
