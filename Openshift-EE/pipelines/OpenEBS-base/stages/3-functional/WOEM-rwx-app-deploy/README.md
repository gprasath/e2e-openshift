### WOEM-Deploy application with rwx PV.

#### Description

Administrator should be able to use this job to deploy application with openebs volumes in read-write-many mode.

#### Prerequisites

- OpenShift cluster should be ready.
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
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/61295">61295</a>   |  Deploy the application using nfs-provisioner accessmode as a readwritemany           |  Fri Jul 19 09:44:36 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'eccdfeaa2967e768c03d0fdf0f206b16c700c80e',type:phrase),type:phrase,value:'eccdfeaa2967e768c03d0fdf0f206b16c700c80e'),query:(match:(commit_id:(query:'eccdfeaa2967e768c03d0fdf0f206b16c700c80e',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'2395',type:phrase),type:phrase,value:'2395'),query:(match:(pipeline_id:(query:'2395',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a>  |