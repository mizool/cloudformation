# Cloudformation

Cloudformation templates and scripts.

## Network architecture

The network template assumes a region with three availability zones.
It will deploy itself into any VPC.
The following visualization assumes, that this network is the only structure inside the VPC.
![VPC architecture](https://raw.githubusercontent.com/mizool/cloudformation/develop/images/public-private-subnets-3az.jpg?sanitize=true&raw=true)

## Creating a release

* Check out `develop`
* Run `mvn -B gitflow:release -DreleaseVersion=<V1> -DdevelopmentVersion=<V2>-SNAPSHOT`
  where `<V1>` is the version you want to release, for example `0.7` and `<V2>` is the next version you want to
  implement for, for example `0.8`.