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


| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90752">90752</a>           |  Check if the snapshot can be rebuilt after loss and recovery of single replica           | Thu Oct  3 11:30:20 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase),type:phrase,value:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb'),query:(match:(commit_id:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3389',type:phrase),type:phrase,value:'3389'),query:(match:(pipeline_id:(query:'3389',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90599">90599</a>           |  Check if the snapshot can be rebuilt after loss and recovery of single replica           | Wed Oct  2 09:13:53 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase),type:phrase,value:'4d5066dddd88c4b57dec1e9eed367c2385e91758'),query:(match:(commit_id:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3386',type:phrase),type:phrase,value:'3386'),query:(match:(pipeline_id:(query:'3386',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90323">90323</a>   |  Check if the snapshot can be rebuilt after loss and recovery of single replica           |  Mon Sep 30 22:20:02 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase),type:phrase,value:'038d3ae24ce0c7364f36918c475e07a98fd15ed0'),query:(match:(commit_id:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3378',type:phrase),type:phrase,value:'3378'),query:(match:(pipeline_id:(query:'3378',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a>  |
