### DTCL-Verify application availability post cstor-target network loss.

#### Description

This test induces network loss on cstor-target conatiner and check if it doesn't affect the application availability.

#### Prerequisites

- D2IQ-Konvoy Cluster should be created and have the dependencies installed.
- cStor based storage pool should have been created.
- OpenEBS storage class should be created with the desired storage pool claim.

#### Procedure

- This job triggers the litmus experiments which induces network loss in cstor-target container and check if the application is not impacted.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly.
- It deploys statefulset application consuming OpenEBS Volume and check if the application is deployed successfully.
- Then, it induces the network loss in cstor target container and verify if the application is running successfully.
- Finally, it deprovisions the statefulset application and update the result.

#### Expected result

Application should be running successfully.

#### Test Result
| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90751">90751</a>           |  Induce cstor target network loss and check if it gets recovered successfully           | Thu Oct  3 11:29:17 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase),type:phrase,value:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb'),query:(match:(commit_id:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3389',type:phrase),type:phrase,value:'3389'),query:(match:(pipeline_id:(query:'3389',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90598">90598</a>           |  Induce cstor target network loss and check if it gets recovered successfully           | Wed Oct  2 09:13:51 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase),type:phrase,value:'4d5066dddd88c4b57dec1e9eed367c2385e91758'),query:(match:(commit_id:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3386',type:phrase),type:phrase,value:'3386'),query:(match:(pipeline_id:(query:'3386',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90322">90322</a>   |  Induce cstor target network loss and check if it gets recovered successfully           |  Mon Sep 30 22:17:32 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase),type:phrase,value:'038d3ae24ce0c7364f36918c475e07a98fd15ed0'),query:(match:(commit_id:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3378',type:phrase),type:phrase,value:'3378'),query:(match:(pipeline_id:(query:'3378',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a>  |
