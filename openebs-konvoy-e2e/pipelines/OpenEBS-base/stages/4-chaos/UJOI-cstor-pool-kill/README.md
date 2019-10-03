#### UJOI-Verify application availablity post cstor-pool pod kill.

#### Description

This test kills the cstor pool pod and check if it doesn't affect the application availability.

#### Prerequisites

- D2IQ-Konvoy Cluster should be created and have the dependencies installed.
- cStor based storage pool should have been created.
- OpenEBS storage class should be created with the desired storage pool claim.

#### Procedure

- This job triggers the litmus experiments which deletes the cstor-pool pod and check if the application is not impacted.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly.
- It deploys statefulset application consuming OpenEBS Volume and check if the application is deployed successfully.
- Then, it deletes the cstor-pool pod and verifies if the application is running successfully.
- Finally, it deprovisions the statefulset application and update the result.

#### Expected result

Application should be running successfully.

#### Test Result
| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/91626">91626</a>           |  Induce failure on cStor pool container(cstor-pool) and check if it is recovered successfully and verify that the application is not impacted           | Thu Oct  3 17:25:01 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'543e795184f8104f4252eb8337d96ec46f9b3d13',type:phrase),type:phrase,value:'543e795184f8104f4252eb8337d96ec46f9b3d13'),query:(match:(commit_id:(query:'543e795184f8104f4252eb8337d96ec46f9b3d13',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3415',type:phrase),type:phrase,value:'3415'),query:(match:(pipeline_id:(query:'3415',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90789">90789</a>           |  Induce failure on cStor pool container(cstor-pool) and check if it is recovered successfully and verify that the application is not impacted           | Thu Oct  3 12:59:10 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase),type:phrase,value:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb'),query:(match:(commit_id:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3390',type:phrase),type:phrase,value:'3390'),query:(match:(pipeline_id:(query:'3390',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90748">90748</a>           |  Induce failure on cStor pool container(cstor-pool) and check if it is recovered successfully and verify that the application is not impacted           | Thu Oct  3 11:22:24 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase),type:phrase,value:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb'),query:(match:(commit_id:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3389',type:phrase),type:phrase,value:'3389'),query:(match:(pipeline_id:(query:'3389',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90595">90595</a>   |  Induce failure on cStor pool container(cstor-pool) and check if it is recovered successfully and verify that the application is not impacted           |  Wed Oct  2 09:13:47 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase),type:phrase,value:'4d5066dddd88c4b57dec1e9eed367c2385e91758'),query:(match:(commit_id:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3386',type:phrase),type:phrase,value:'3386'),query:(match:(pipeline_id:(query:'3386',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a>  |
