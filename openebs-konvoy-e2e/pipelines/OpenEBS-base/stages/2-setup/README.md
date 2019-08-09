### Goal of this stage

The goal of this gitlab stage is to deploy OpenEBS components in OpenShift cluster and create the storage pools.

### Test Cases in OpenEBS-Setup Stage

The test cases in OpenEBS-Setup stage are as follows:

| S.No | TID  | Test case description                                        |
| ---- | ---- | ------------------------------------------------------------ |
| 1    | O21Y | Deploy OpenEBS in OpenShift-EE-3.10 Cluster                  |
| 2    | ZNSF | Create K8s storage classes adhering the policies supported by OpenEBS |
| 3    | XC0I | Create cStor based Striped storage pool on disks.            |
| 4    | XH12 | Create cStor based storage pool of type mirrored             |

