### WVFD- Scaling up statefulset application replicas

#### Description

This test ensures that the application replicas can be scaled by updating its corresponding deployment.

#### Prerequisites

- Konvoy Cluster should be created and have the dependencies installed.
- cStor based storage pool should have been created.
- OpenEBS storage class should be created with the desired storage pool claim.

#### Procedure

- This job triggers the litmus experiments which scales up application replica and ensures that the scaled replica consumes OpenEBS storage volume.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly.
- This job deploy busybox statefulset application with two replicas using OpenEBS storage class and start data traffic in the application pod.
- Then it attempts to increase the application replica count to three using `kubectl scale` command.
- Finally, it Check if the new application pod is created and the ring is formed.

#### Expected result

- The new application replica should be created successfully.

#### Test Result
| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90120">90120</a>   |  Scale the statefulset application replicas and verify the ring configuration           |  Mon Sep 30 13:09:52 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9',type:phrase),type:phrase,value:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9'),query:(match:(commit_id:(query:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3372',type:phrase),type:phrase,value:'3372'),query:(match:(pipeline_id:(query:'3372',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a>  |
