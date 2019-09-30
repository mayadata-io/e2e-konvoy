### XXXC-Restricting Parent volume deletion in presence of clones.

#### Description

The intention of this test is to ensure that the parent volumes are not deletable in presence of its clones.

#### Prerequisites

- Konvoy Cluster should be created and have the dependencies installed.
- cStor based storage pool should have been created.
- OpenEBS storage class should be created with the desired storage pool claim.

#### Procedure

- This job triggers the litmus experiments which checks if OpenEBS admission server blocks the deletion of parent volume when it has descendants.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly.
- The next litmus experiment creates snapshot of OpenEBS persistent volume and create clone using the snapshot.
- Then, the job attempts to delete the parent volume which has snapshot and clone.
- OpenEBS admission controller should prevent the deletion by throwing appropriate error message.
- Finally, this job updates the result CR with the actual result.

#### Expected result

- The volume snapshot should be created successfully.
- The clone should be created successfully.
- The parent volume should not be deleted and throw appropriate error message.

#### Test Result
| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90122">90122</a>   |  Check if the clone can be created using volume snapshot           |  Mon Sep 30 13:05:03 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9',type:phrase),type:phrase,value:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9'),query:(match:(commit_id:(query:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3372',type:phrase),type:phrase,value:'3372'),query:(match:(pipeline_id:(query:'3372',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a>  |
