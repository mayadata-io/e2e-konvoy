### HVFC-Snapshot rebuilding

#### Description

This test ensures if the snapshot can be rebuilt after recovering a replica from failure

#### Prerequisites

- D2IQ-Konvoy Cluster should be created and have the dependencies installed.
- cStor based storage pool should have been created.
- OpenEBS storage class should be created with the desired storage pool claim.

#### Procedure

- This job triggers the litmus experiments which checks if the snapshot can be rebuilt after recovering a replica from failure.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly.
- It induces delay in one of the cstor pool pods using the tool tc and disconnects it from the target. Meanwhile tries to create a snapshot which will not be created it the disconnected replica.
- Then, recovers the replica from failure and check if it starts snapshot rebulding.
- Once snapshot is rebuilt successfully, updates the result to the CR.

#### Expected result

- Snapshot should be rebuilt successfully on the replica after it recovers from failure.

#### Test result

