OpenEBS Chaos stage covers various chaos tests performed on OpenEBS storage engine components.

The test cases in the Chaos stage are as follows:



| S.No | TID  | Test Description                                             |
| ---- | ---- | ------------------------------------------------------------ |
| 1    | MCDE | Induce application failure on application consuming cStor volume and check if gets recovered successfully. |
| 2    | QRSG | Verify application availability post cstor-pool-mgmt conatiner kill |
| 3    | HVFC | Check if the snapshot can be rebuilt after recovering a replica from failure |
| 4    | DBVQ | Verify application availability post cStor pool pod failure. |
| 5    | CVHY | Verify application availability post cstor-pool network delay. |
| 6    | NSCD | Verifying application HA consuming jiva volume post application pod kill. |
| 7    | OHQP | Verify application availability post cstor-target network delay. |
| 8    | MVET | Fail jiva replica pod in single replica deployment.          |
| 9    | UJOI | Verify application availability post cstor-pool pod kill.    |
| 10   | ACME | Verify application availability post cstor target istgt container kill. |
| 11   | ZGNK | Verify Jiva replica stickiness to node.                      |
| 12   | DTCL | Verify application availability post cstor-target network loss. |
| 13   | TZZP | Verify application HA post jiva controller network delay.    |
| 13   | REUZ | Ensure application availability upon failing a jiva replica pod |
| 14   | FQFO | Verify application availability post jiva controller failure |
| 15   | WPZU | Verify application availability post cstor target pod kill.  |
| 16   | LGHO |                                                              |
| 17   | EWXO |                                                              |
| 18   | RFWB |                                                              |
| 19   | QOTC |                                                              |
| 20   | BLKK |                                                              |
| 21   | REGN |                                                              |
| 22   | IVQM |                                                              |
| 23   | GBVT |                                                              |
| 24   | YCOR |                                                              |
| 25   | WSVN |                                                              |
| 26   |      |                                                              |

