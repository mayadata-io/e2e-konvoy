### PCZD-Setting up D2IQ-Konvoy cluster.

#### Description

The Administrator should be able to use this job to configure konvoy cluster and check if it is healthy for carrying out e2e tests.

#### Prerequisites

- The host machines should be created and have the dependent packages installed in all the machines.

#### Procedure

- This job triggers a litmus experiment which configures konvoy cluster using its corresponding inventory.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the inventory accordingly.
- This test should check if the konvoy cluster is ready using kubectl command ```kubectl get nodes```

#### Expected result

- Konvoy cluster should be configured successfully. All the nodes in the cluster should be in healthy state. 

#### Test Result

