# OpenEBS-base e2e Tests on D2IQ-Konvoy platform

This directory covers the test case development status for E2E certification of OpenEBS Enterprise Edition on Day2IQ-Konvoy platform.

The test cases are divided as per the Stages that run in GitLab pipeline. Following are the stages.

| Stage            | Description                                                  |
| ---------------- | ------------------------------------------------------------ |
| Cluster-Creation | Test cases for setting up OpenShift cluster. This is currently being done in the OnPrem Lab where Kubernetes nodes are provisioned on the VMware vSphere platform |
| OpenEBS-Setup    | Test cases for installing OpenEBS, creation of storage pools and storage classes |
| Functional test  | All test cases for testing basic functionality of OpenEBS control plane components (API server, provisioner and metrics exporters), data plane components (Jiva and cStor) and NDM |
| Chaos test       | All test cases to introduce various types of chaos into either Kubernetes platform or OpenEBS control/data plane or stateful application |
| Cleanup          | Test cases for cleaning up the cluster resources that were setup during the first stage |

