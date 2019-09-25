### Goal of this stage

The goal of this gitlab stage is to carry out OpenEBS data and control plane functionality tests in Konvoy Cluster test bed.

### Test cases matrix:

The test cases covered in the functional stage are as follows:

| S.No | TID  | Test case description                                        |
| ---- | ---- | ------------------------------------------------------------ |
| 1    | QUSX | Check if an application can be deployed using jiva storage engine |
| 2    | PLIR | Check if the clone can be created using cstor volume snapshot |
| 3    | MRRB | Ensure the data integrity in openebs cstor volume using fio. |
| 4    | NLON | Check if the memory consumption in cstor target doesn't cross the desired threshold for known workload. |
| 5    | XXXC | Make sure that the parent volume cannot be deleted in presence of its clones. |
| 6    | AVNT | Check if the storage replicas can be scaled up.              |
| 7    | TIXL | Check if the volume can be filled completely.                |
| 8    | XZDZ | Check if the storage volume replicas are distributed across the storage pools in case of statefulset deployment. |
| 9    | NFLR | Scale the statefulset application replicas and verify the ring configuration. |
| 10   | CRQX | Check if the target pod gets scheduled on the node where the application pod is running adhering target pod affinity. |
| 11   | JKAB | Check if the memory consumption in jiva controller doesn't cross the desired threshold for known workload. |
| 12   | KUSP | Deploy Application using storage class with specific CAS parameters. |
| 13   | ISBE | Deploy jiva data plane pods in openebs namespace             |
| 14   | MBKO | Attempting to create clone with different capacity           |
| 15   | LLJA | Verify Jiva-Internal-Snapshot Deletion                       |
| 16   | USGA | Creating snapshot for Jiva Volume                            |
| 17   | XBRF | Verify if the application pod and jiva controller are scheduled on same node. |
| 18   | POXG | Verify if the statefulset application and cStor target are scheduled on same node |
| 19   | CCRT | Verify if the application consuming Jiva storage can be scaled up. |
| 20   | WVFD | Scaling up statefulset application replicas                  |
| 21   | UAFE | Deploy application with rwx PV.                              |
| 22   | NWVV |                                                              |
