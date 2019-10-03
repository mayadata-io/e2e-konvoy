### TIXL-Fill OpenEBS cStor volume with data.

#### Description

The job fills the cStor volume with data.

#### Prerequisites

- Konvoy cluster should be created.
- OpenEBS should be deployed in K8s cluster.
- cStor Storage pool should be created.

#### Procedure

- This job triggers the litmus experiments which is capable of deploying busybox application using OpenEBS volumes, filling the volume and deprovision the volume.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest accordingly.
- The first litmus experiment deploys busybox application and verifies if it is deployed successfully.
- The preceding litmus experiment uses fio tool to pump io traffic and checks if there is any io error.
- It also checks if the data can be filled upto the maximum capacity of volume.
- Finally, this job updates the result CR with the actual result.

#### Expected result

- The busybox application should be deployed successfully.
- The volume should be filled upto maximum capacity without any errors.
- Deprovisioning the application and its corresponding PVC should be successful.

#### Test Result
| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90739">90739</a>           |  Fill cstor volume completely and check if its size can be scaled seamlessly           | Thu Oct  3 11:01:54 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase),type:phrase,value:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb'),query:(match:(commit_id:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3389',type:phrase),type:phrase,value:'3389'),query:(match:(pipeline_id:(query:'3389',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90586">90586</a>           |  Fill cstor volume completely and check if its size can be scaled seamlessly           | Wed Oct  2 08:41:29 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase),type:phrase,value:'4d5066dddd88c4b57dec1e9eed367c2385e91758'),query:(match:(commit_id:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3386',type:phrase),type:phrase,value:'3386'),query:(match:(pipeline_id:(query:'3386',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90310">90310</a>   |  Fill cstor volume completely and check if its size can be scaled seamlessly           |  Mon Sep 30 21:12:43 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase),type:phrase,value:'038d3ae24ce0c7364f36918c475e07a98fd15ed0'),query:(match:(commit_id:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3378',type:phrase),type:phrase,value:'3378'),query:(match:(pipeline_id:(query:'3378',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a>  |
