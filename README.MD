# Packer build image

Image is based on the official CentOS 7 AMI

Packer template: [centos-base.json](centos-base.json)

Before running the build, make sure that you've configured `AWS_ACCESS_KEY` and `AWS_SECRET_ACCESS_KEY` in your shell. You can put into `~/.aws/credentials` config file or specify it as env variables `export AWS_ACCESS_KEY` and `export AWS_SECRET_ACCESS_KEY`.


## Goss provisioner

We use goss utility to test our built image. Packer doesn't provide goss provisioner from box. You need to install provisioner goss packer plugin.
All information you can find here: https://github.com/YaleUniversity/packer-provisioner-goss

## Validation
Use following command to validate your packer configuration:
```
packer inspect centos-base.json
packer validate centos-base.json
```

## Build

```sh
packer build base.json
```