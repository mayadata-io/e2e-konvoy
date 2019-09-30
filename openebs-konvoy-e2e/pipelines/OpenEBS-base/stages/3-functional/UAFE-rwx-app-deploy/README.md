### UAFE-Deploy application with rwx PV.

#### Description

Administrator should be able to use this job to deploy application with openebs volumes in read-write-many mode.

#### Prerequisites

-  cluster should be ready.
- OpenEBS should be deployed in cluster.
- Openebs cstor pool should be created.
- nfs provisioner should be deployed.

#### Procedure

- This job triggers litmus experiment which deploys application with openebs volumes in read-write-many mode.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest accordingly.
- Litmus experiment checks if the application deployment is successful.
- Finally, this job updates the result CR with the actual result.

#### Expected result

- Application deployment should be successful in rwx mode.

#### Test Result
| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
|     <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90311">90311</a>           |  Deploy the application using nfs-provisioner accessmode as a readwritemany           | Mon Sep 30 21:14:16 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase),type:phrase,value:'038d3ae24ce0c7364f36918c475e07a98fd15ed0'),query:(match:(commit_id:(query:'038d3ae24ce0c7364f36918c475e07a98fd15ed0',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3378',type:phrase),type:phrase,value:'3378'),query:(match:(pipeline_id:(query:'3378',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a> |
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-konvoy/-/jobs/90118">90118</a>   |  Deploy the application using nfs-provisioner accessmode as a readwritemany           |  Mon Sep 30 13:00:51 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9',type:phrase),type:phrase,value:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9'),query:(match:(commit_id:(query:'c64ef57e64904d2d3b10ac9bb38fd0925adfe2a9',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'3372',type:phrase),type:phrase,value:'3372'),query:(match:(pipeline_id:(query:'3372',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a>  |
