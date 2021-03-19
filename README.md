# helm-core-template

This is a Library Helm Chart that is a PoC for using a remote repo as
the core of a set of application Helm charts.

Values and resources set up here are intended to be used by the "child"
applications, with additions and variations as needed.

To change the provided template, package the template and update the index 
so this repository can be used as a Helm repo:

```shell
# Package Library Chart
$ helm package core-template/

# Create/Update index.yaml 
$ helm repo index .
```

To use this repository as a Helm repo:

```shell
$ helm repo add [desired-helm-repo-name] [URL] [flags]
```

Example:

```shell
$ helm repo add github-helm-repo 'https://raw.githubusercontent.com/SkylarScaling/helm-core-template/master/' --password <git-token> --username SkylarScaling
```