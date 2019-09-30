### MBKO-Attempting to create clone with different capacity

#### Description

This test ensures that the clone volume can not be created if the capacity is different.

#### Prerequisites

- Konvoy Cluster should be created and have the dependencies installed.
- cStor based storage pool should have been created.
- OpenEBS storage class should be created with the desired storage pool claim.

#### Procedure

- This job triggers the litmus experiments which creates clone volume using volume snapshot.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly. Update the clone capacity with value other than capacity of actual PV.
- This job checks if the provided snapshot is created in the cluster and snapshot-promoter storageclass is created.
- It updates the clone template with the input parameters such as snapshot name, storage class and the application namespace.
- Use clone creation utility to create clone.
- Finally, it checks if the cloned volume is not created . In OpenEBS, admission-controller should block clone creation if the capacity is different.

#### Expected result

- The clone volume should not be created if the capacity is different than the PV capacity.

#### Test Result
| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90113">90113</a>   |  Check if the clone can't be created with different volume capacity           |  Mon Sep 30 13:04:31 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9',type:phrase),type:phrase,value:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9'),query:(match:(commit_id:(query:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3372',type:phrase),type:phrase,value:'3372'),query:(match:(pipeline_id:(query:'3372',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a>  |
