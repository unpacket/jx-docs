---
date: 2019-08-22T13:59:53Z
title: "jx install"
slug: jx_install
url: /commands/jx_install/
---
## jx install

Install Jenkins X in the current Kubernetes cluster

### Synopsis

Installs the Jenkins X platform on a Kubernetes cluster 

Requires a --git-username and --git-api-token that can be used to create a new token. This is so the Jenkins X platform can git tag your releases 

For more documentation see: https://jenkins-x.io/getting-started/install-on-cluster/

The current requirements are: 

 *RBAC is enabled on the cluster 

 *Insecure Docker registry is enabled for Docker registries running locally inside Kubernetes on the service IP range. See the above documentation for more detail

```
jx install [flags]
```

### Examples

```
  # Default installer which uses interactive prompts to generate git secrets
  jx install
  
  # Install with a GitHub personal access token
  jx install --git-username jenkins-x-bot --git-api-token 9fdbd2d070cd81eb12bca87861bcd850
  
  # If you know the cloud provider you can pass this as a CLI argument. E.g. for AWS
  jx install --provider=aws
```

### Options

```
      --advanced-mode                         Advanced install options. This will prompt for advanced install options
      --aws-access-key-id string              Access key id of service account to be used by vault
      --aws-dynamodb-region string            The region to use for storing values in AWS DynamoDB
      --aws-dynamodb-table string             The table in AWS DynamoDB to use for storing values (default "vault-data")
      --aws-kms-key-id string                 The ID or ARN of the AWS KMS key to encrypt values
      --aws-kms-region string                 The region of the AWS KMS key to encrypt values
      --aws-s3-bucket string                  The name of the AWS S3 bucket to store values in
      --aws-s3-prefix string                  The prefix to use for storing values in AWS S3 (default "vault-operator")
      --aws-s3-region string                  The region to use for storing values in AWS S3
      --aws-secret-access-key string          Secret access key of service account to be used by vault
      --azure-acr-subscription string         The Azure subscription under which the specified docker-registry is located
      --buildpack string                      The name of the build pack to use for the Team
      --cleanup-temp-files                    Cleans up any temporary values.yaml used by helm install [default true] (default true)
      --cloud-environment-repo string         Cloud Environments Git repo (default "https://github.com/jenkins-x/cloud-environments")
      --cloudbees-auth string                 Auth used when setting up a letter/tenant cluster, format: 'username:password'
      --cloudbees-domain string               When setting up a letter/tenant cluster, this creates a tenant cluster on the cloudbees domain which is retrieved via the required URL
      --config-file string                    Configuration file used for installation
      --default-admin-password string         the default admin password to access Jenkins, Kubernetes Dashboard, ChartMuseum and Nexus
      --default-admin-username string         the default admin username to access Jenkins, Kubernetes Dashboard, ChartMuseum and Nexus (default "admin")
      --default-environment-prefix string     Default environment repo prefix, your Git repos will be of the form 'environment-$prefix-$envName'
      --docker-registry string                The Docker Registry host or host:port which is used when tagging and pushing images. If not specified it defaults to the internal registry unless there is a better provider default (e.g. ECR on AWS/EKS)
      --docker-registry-org string            The Docker Registry organiation/user to create images inside. On GCP this is typically your Google Project ID.
      --domain string                         Domain to expose ingress endpoints.  Example: jenkinsx.io
      --draft-client-only                     Only install draft client
      --environment-git-owner string          The Git provider organisation to create the environment Git repositories in
      --exposecontroller-pathmode path        The ExposeController path mode for how services should be exposed as URLs. Defaults to using subnets. Use a value of path to use relative paths within the domain host such as when using AWS ELB host names
      --exposecontroller-urltemplate string   The ExposeController urltemplate for how services should be exposed as URLs. Defaults to being empty, which in turn defaults to "{{.Service}}.{{.Namespace}}.{{.Domain}}".
      --exposer string                        Used to describe which strategy exposecontroller should use to access applications (default "Ingress")
      --external-dns                          Installs external-dns into the cluster. ExternalDNS manages service DNS records for your cluster, providing you've setup your domain record
      --external-ip string                    The external IP used to access ingress endpoints from outside the Kubernetes cluster. For bare metal on premise clusters this is often the IP of the Kubernetes master. For cloud installations this is often the external IP of the ingress LoadBalancer.
      --git-api-token string                  The Git API token to use for creating new Git repositories
      --git-private                           Create new Git repositories as private
      --git-provider-kind string              Kind of Git server. If not specified, kind of server will be autodetected from Git provider URL. Possible values: bitbucketcloud, bitbucketserver, gitea, gitlab, github, fakegit
      --git-provider-url string               The Git server URL to create new Git repositories inside (default "https://github.com")
      --git-username string                   The Git username to use for creating new Git repositories
      --gitops                                Creates a git repository for the Dev environment to manage the installation, configuration, upgrade and addition of Apps in Jenkins X all via GitOps
      --global-tiller                         Whether or not to use a cluster global tiller (default true)
      --helm-client-only                      Only install helm client
      --helm-tls                              Whether to use TLS with helm
      --helm3                                 Use helm3 to install Jenkins X which does not use Tiller
  -h, --help                                  help for install
      --ingress-class string                  Used to set the ingress.class annotation in exposecontroller created ingress
      --ingress-cluster-role string           The cluster role for the Ingress controller (default "cluster-admin")
      --ingress-deployment string             The name of the Ingress controller Deployment (default "jxing-nginx-ingress-controller")
      --ingress-namespace string              The namespace for the Ingress controller (default "kube-system")
      --ingress-service string                The name of the Ingress controller Service (default "jxing-nginx-ingress-controller")
      --install-dependencies                  Enables automatic dependencies installation when required
      --install-only                          Force the install command to fail if there is already an installation. Otherwise lets update the installation
      --kaniko                                Use Kaniko for building docker images
      --keep-exposecontroller-job             Prevents Helm deleting the exposecontroller Job and Pod after running.  Useful for debugging exposecontroller logs but you will need to manually delete the job if you update an environment
      --knative-build                         Note this option is deprecated now in favour of tekton. If specified this will keep using the old knative build with Prow instead of the strategic tekton
      --local-cloud-environment               Ignores default cloud-environment-repo and uses current directory 
      --local-helm-repo-name string           The name of the helm repository for the installed ChartMuseum (default "releases")
      --long-term-storage                     Enable the Long Term Storage option to save logs and other assets into a GCS bucket (supported only for GKE)
      --lts-bucket string                     The bucket to use for Long Term Storage. If the bucket doesn't exist, an attempt will be made to create it, otherwise random naming will be used
      --namespace string                      The namespace the Jenkins X platform should be installed into (default "jx")
      --ng                                    Use the Next Generation Jenkins X features like Prow, Tekton, No Tiller, Vault, Dev GitOps
      --no-brew                               Disables brew package manager on MacOS when installing binary dependencies
      --no-default-environments               Disables the creation of the default Staging and Production environments
      --no-gitops-env-apply                   When using GitOps to create the source code for the development environment and installation, don't run 'jx step env apply' to perform the install
      --no-gitops-env-repo                    When using GitOps to create the source code for the development environment this flag disables the creation of a git repository for the source code
      --no-gitops-env-setup                   When using GitOps to install the development environment this flag skips the post-install setup
      --no-gitops-vault                       When using GitOps to create the source code for the development environment this flag disables the creation of a vault
      --no-tiller                             Whether to disable the use of tiller with helm. If disabled we use 'helm template' to generate the YAML from helm charts then we use 'kubectl apply' to install it to avoid using tiller completely. (default true)
      --on-premise                            If installing on an on premise cluster then lets default the 'external-ip' to be the Kubernetes master IP address
      --provider string                       Cloud service providing the Kubernetes cluster.  Supported providers: aks, alibaba, aws, eks, gke, icp, iks, jx-infra, kubernetes, minikube, minishift, oke, openshift, pks
      --prow                                  Enable Prow to implement Serverless Jenkins and support ChatOps on Pull Requests
      --recreate-existing-draft-repos         Delete existing helm repos used by Jenkins X under ~/draft/packs
      --register-local-helmrepo               Registers the Jenkins X ChartMuseum registry with your helm client [default false]
      --remote-environments                   Indicates you intend Staging and Production environments to run in remote clusters. See https://jenkins-x.io/getting-started/multi-cluster/
      --remote-tiller                         If enabled and we are using tiller for helm then run tiller remotely in the kubernetes cluster. Otherwise we run the tiller process locally. (default true)
      --skip-auth-secrets-merge               Skips merging the secrets from local files with the secrets from Kubernetes cluster
      --skip-cluster-role                     Don't enable cluster admin role for user
      --skip-ingress                          Skips the installation of ingress controller. Note that a ingress controller must already be installed into the cluster in order for the installation to succeed
      --skip-setup-tiller                     Don't setup the Helm Tiller service - lets use whatever tiller is already setup for us.
      --static-jenkins                        Install a static Jenkins master to use as the pipeline engine. Note this functionality is deprecated in favour of running serverless Tekton builds
      --tekton                                Enables the Tekton pipeline engine (which used to be called knative build pipeline) along with Prow to provide Serverless Jenkins. Otherwise we default to use Knative Build if you enable Prow
      --tiller-cluster-role string            The cluster role for Helm's tiller (default "cluster-admin")
      --tiller-namespace string               The namespace for the Tiller when using a global tiller (default "kube-system")
      --timeout string                        The number of seconds to wait for the helm install to complete (default "6000")
      --urltemplate string                    For ingress; exposers can set the urltemplate to expose
      --user-cluster-role string              The cluster role for the current user to be able to administer helm (default "cluster-admin")
      --username string                       The Kubernetes username used to initialise helm. Usually your email address for your Kubernetes account
      --vault                                 Sets up a Hashicorp Vault for storing secrets during installation (supported only for GKE)
      --vault-bucket-recreate                 If the vault bucket already exists delete it then create it empty (default true)
      --version string                        The specific platform version to install
      --versions-ref string                   Jenkins X versions Git repository reference (tag, branch, sha etc)
      --versions-repo string                  Jenkins X versions Git repo (default "https://github.com/jenkins-x/jenkins-x-versions.git")
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx](/commands/jx/)	 - jx is a command line tool for working with Jenkins X
* [jx install dependencies](/commands/jx_install_dependencies/)	 - Install missing dependencies

###### Auto generated by spf13/cobra on 22-Aug-2019
