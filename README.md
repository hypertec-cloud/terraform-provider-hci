# terraform-provider-hci [![Build Status](https://github.com/hypertec-cloud/terraform-provider-hci/workflows/build/badge.svg)](https://github.com/hypertec-cloud/terraform-provider-hci/actions) [![GoDoc](https://godoc.org/github.com/hypertec-cloud/terraform-provider-hci?status.svg)](https://godoc.org/github.com/hypertec-cloud/terraform-provider-hci) [![Go Report Card](https://goreportcard.com/badge/github.com/hypertec-cloud/terraform-provider-hci)](https://goreportcard.com/report/github.com/hypertec-cloud/terraform-provider-hci) [![license](https://img.shields.io/github/license/hypertec-cloud/terraform-provider-hci)](https://github.com/hypertec-cloud/terraform-provider-hci/blob/master/LICENSE)


Terraform provider for hypertec.cloud

Tested with Terraform version : 1.0.11


## How to use this provider

To install this provider, copy and paste this code into your Terraform configuration. Then, run terraform init.

#### Terraform 0.13+
```
terraform {
  required_providers {
    hci = {
      source = "hypertec-cloud/hci"
      version = "1.0.0"
    }
  }
}

provider "hci" {
  # Configuration options
}
```
## Alternate installations

1. Download the hypertec.cloud Terraform provider binary for your OS from the [releases page](https://github.com/hypertec-cloud/terraform-provider-hci/releases).
2. Copy the provider to the plugin directory `~/.terraform.d/plugins`.

Alternate: [Terraform documentation](https://www.terraform.io/docs/plugins/basics.html)

## How to use

In your configuration file, define a variable that will hold your API key. This variable will have the value of the environment variable `TF_VAR_my_api_key`. Create a new "hci" provider with the `api_key`. Optionally, you can override the `api_url` field of the provider.

```hcl
variable "my_api_key" {}

provider "hci" {
    api_key = "${var.my_api_key}"
}
```

## Links

- [**Resources documentation**](https://github.com/hypertec-cloud/terraform-provider-hci/tree/master/docs/resources)
- [**Terraform registry**](https://registry.terraform.io/providers/hypertec-cloud/hci/latest)
## Build from source

Install [Go](https://golang.org/doc/install) (version 1.12 is required)

Download the provider source:

```Shell
go get github.com/hypertec-cloud/terraform-provider-hci
```

Compile the provider:

```Shell
cd $GOPATH/src/github.com/hypertec-cloud/terraform-provider-hci
make build
```

Copy the provider to the directory where terraform is located:

```Shell
sudo cp ./bin/$(go env GOOS)-$(go env GOARCH)/terraform-provider-hci_* $(dirname `which terraform`)
```

## Build for all OS/architectures

To build zip files containing the executables for each OS/architecture combination, use

```Shell
make build-all
```

## Prepare a Release

To prepare a new release, use one of the following:

```shell
make patch # e.g. move from v1.2.3 to v1.2.4
make minor # e.g. move from v1.2.3 to v1.3.0
make major # e.g. move from v1.2.3 to v2.0.0
```

or

```shell
make release version=x.y.z # where x, y and z are non-negative integers
```

also you can use `push=true` flag in all of the above to push the newly released tag to GitHub.

## License

This project is licensed under the terms of the MIT license.

```text
The MIT License (MIT)

Copyright (c) 2019 CloudOps

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
