### Goal of this stage

The goal of this gitlab stage is to deploy OpenEBS components in Konvoy cluster and create the storage pools.

### Test Cases in OpenEBS-Setup Stage

The test cases in OpenEBS-Setup stage are as follows:

| S.No | TID  | Test case description                                        |
| ---- | ---- | ------------------------------------------------------------ |
| 1    | XJGT | Deploy OpenEBS in Konvoy Cluster                             |
| 2    | PIGE | Create K8s storage classes adhering the policies supported by OpenEBS |
| 3    | GZTK | Create cStor based Striped storage pool on disks.            |
| 4    | GCLC | Create cStor based storage pool of type mirrored             |
| 5    | AMHE | Create cStor based storage pool of type raidz1               |
| 6    | KSDJ | Create cStor based storage pool of type raidz2               |
| 7    | OQEW | Deploy NFS provisioner on konvoy cluster                     |
| 8    | HODS | Deploy CSI provisioner on konvoy cluster                     |

