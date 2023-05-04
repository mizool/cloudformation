# Cloudformation

Cloudformation templates and scripts.

## Network architecture

The network template assumes a region with three availability zones.
It will deploy itself into any VPC.
The following visualization assumes, that this network is the only structure inside the VPC.
![VPC architecture](https://raw.githubusercontent.com/mizool/cloudformation/develop/images/public-private-subnets-3az.jpg?sanitize=true&raw=true)

## Creating a release

* Check out `develop`.
* Run `mvn -B gitflow:release -DreleaseVersion=<V1> -DdevelopmentVersion=<V2>-SNAPSHOT`
  where `<V1>` is the version you want to release, for example `0.7` and `<V2>` is the next version you want to
  implement for, for example `0.8`.

## Performing a hotfix

### Start
* Check out `master`.
* Run `mvn -B gitflow:hotfix-start -DhotfixVersion=<V1>` where `<V1>` is the version you want the hotfix to have, for example `0.7.1`.

### Fix
* Perform your fix, either directly on the new `hotfix/<V1>` branch or by merging another branch to that hotfix branch.

### Finish
* ⚠️ Make sure the hotfix branch is pushed to `origin` before you proceed. Local changes will get lost! ⚠️
* Check out the `hotfix/<V1>` branch.
* Run `mvn gitflow:hotfix-finish`.