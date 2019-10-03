### MCDE-Verifying application HA post application pod kill.

#### Description

This job ensures that the application runs seamlessly on inducing the application pod kill.

#### Prerequisites

- D2IQ-Konvoy Cluster should be created and have the dependencies installed.
- cStor based storage pool should have been created.
- OpenEBS storage class should be created with the desired storage pool claim

#### Procedure

- This job triggers the litmus experiments which induces failure on one of the application pods and ensures that there is no impact.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly.
- This job deploys busybox statefulset application consuming OpenEBS Volume and checks if the application is deployed successfully.
- Then it induces application pod kill chaos and verify if the application pod is rescheduled and running successfully.
- Finally, the job deletes the busybox deployment.

#### Expected result

- Application pod should be rescheduled successfully.


#### Test Result

| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/91625">91625</a>           |  Induce application pod failure and check if it is recovered successfully           | Thu Oct  3 17:22:42 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'543e795184f8104f4252eb8337d96ec46f9b3d13',type:phrase),type:phrase,value:'543e795184f8104f4252eb8337d96ec46f9b3d13'),query:(match:(commit_id:(query:'543e795184f8104f4252eb8337d96ec46f9b3d13',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3415',type:phrase),type:phrase,value:'3415'),query:(match:(pipeline_id:(query:'3415',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90788">90788</a>           |  Induce application pod failure and check if it is recovered successfully           | Thu Oct  3 12:59:06 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase),type:phrase,value:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb'),query:(match:(commit_id:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3390',type:phrase),type:phrase,value:'3390'),query:(match:(pipeline_id:(query:'3390',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90747">90747</a>           |  Induce application pod failure and check if it is recovered successfully           | Thu Oct  3 11:22:24 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase),type:phrase,value:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb'),query:(match:(commit_id:(query:'5f9fa424f3c1570a5bb3444c4a22aa971d8e3dcb',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3389',type:phrase),type:phrase,value:'3389'),query:(match:(pipeline_id:(query:'3389',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90594">90594</a>           |  Induce application pod failure and check if it is recovered successfully           | Wed Oct  2 09:13:45 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase),type:phrase,value:'4d5066dddd88c4b57dec1e9eed367c2385e91758'),query:(match:(commit_id:(query:'4d5066dddd88c4b57dec1e9eed367c2385e91758',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3386',type:phrase),type:phrase,value:'3386'),query:(match:(pipeline_id:(query:'3386',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a> |
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90317">90317</a>   |  Induce application pod failure and check if it is recovered successfully           |  Mon Sep 30 22:17:34 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase),type:phrase,value:'038d3ae24ce0c7364f36918c475e07a98fd15ed0'),query:(match:(commit_id:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3378',type:phrase),type:phrase,value:'3378'),query:(match:(pipeline_id:(query:'3378',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a>  |
