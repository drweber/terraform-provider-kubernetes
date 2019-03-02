# Terraform Provider

This provider is a **fork** of the official Kubernetes provider developed by HashiCorp.
This fork supports the following resources in addition to the official provider:

- Ingress `kubernetes_ingress` [taken_from_sl1pm4t_github](https://github.com/sl1pm4t/terraform-provider-kubernetes/)

## Supported Kubernetes Versions

The latest build of this provider uses v6.0 of the kubernetes [client-go](https://github.com/kubernetes/client-go) library, and has been tested with the following Kubernetes versions:

- 1.7.x
- 1.8.x
- 1.9.x
- 1.10.x
- 1.11.x

## Terraform 
- Website: https://www.terraform.io
- [![Gitter chat](https://badges.gitter.im/hashicorp-terraform/Lobby.png)](https://gitter.im/hashicorp-terraform/Lobby)
- Mailing list: [Google Groups](http://groups.google.com/group/terraform-tool)

<img src="https://cdn.rawgit.com/hashicorp/terraform-website/master/content/source/assets/images/logo-hashicorp.svg" width="600px">


## Requirements


-	[Terraform](https://www.terraform.io/downloads.html) 0.10.x
-	[Go](https://golang.org/doc/install) 1.9 (to build the provider plugin)

## Building The Provider

Clone repository to: `$GOPATH/src/github.com/terraform-providers/terraform-provider-kubernetes`

```sh
$ mkdir -p $GOPATH/src/github.com/terraform-providers; cd $GOPATH/src/github.com/terraform-providers
$ git clone git@github.com:terraform-providers/terraform-provider-kubernetes
```

Enter the provider directory and build the provider

```sh
$ cd $GOPATH/src/github.com/terraform-providers/terraform-provider-kubernetes
$ make build
```

## Using the provider

- [ ] Fill in for each provider

## Developing the Provider

### Contributing Resources

In order to prevent breaking changes and migration of user-created resources, resources included in this provider will be limited to `v1` APIs and not `alpha` or `beta`. You can find `v1` resources in the Kubernetes [API documentation](https://kubernetes.io/docs/reference/#api-reference) for the appropriate version of Kubernetes.

### Development Environment

If you wish to work on the provider, you'll first need [Go](http://www.golang.org) installed on your machine (version 1.9+ is *required*). You'll also need to correctly setup a [GOPATH](http://golang.org/doc/code.html#GOPATH), as well as adding `$GOPATH/bin` to your `$PATH`.

To compile the provider, run `make build`. This will build the provider and put the provider binary in the `$GOPATH/bin` directory.

```sh
$ make build
...
$ $GOPATH/bin/terraform-provider-kubernetes
...
```

In order to test the provider, you can simply run `make test`.

```sh
$ make test
```

In order to run the full suite of Acceptance tests, run `make testacc`.

*Note:* Acceptance tests create real resources, and often cost money to run.

```sh
$ make testacc
```
