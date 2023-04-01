"This Project has been archived by the owner, who is no longer providing support.  The project remains available to authorized users on a "read only" basis."

# Global Scheduler

[![Go Report Card](https://goreportcard.com/badge/github.com/futurewei-cloud/arktos)](https://goreportcard.com/report/github.com/futurewei-cloud/arktos)
[![LICENSE](https://img.shields.io/badge/license-apache%202.0-green)](https://github.com/futurewei-cloud/arktos/blob/master/LICENSE)

## What Global Scheduler is

Global Scheduler is an open source global scheduling management system designed for large scale clouds.
It helps coordinate resource consumption among multi cloud data centers and edge sites, and intelligently
place workloads on the best DC or edge site based on traffic patterns and global resource availability
It is evolved from the open source [Kubernetes](https://github.com/kubernetes/kubernetesh) v1.15 codebase
with some fundamental improvements.

Global Scheduler aims to address key scheduling challenges of compute units (e.g. VM and containers) across
a large number of DC clouds and edge clouds---system scalability, resource sharing, resource efficiency, 
scheduling rate/latency, application-performance-aware scheduling, etc.  

----

## Key Features of Global Scheduler


### Large Scalability

Global Scheduler achieves a scalable architecture by partitioning and replicating system components, including API Server, storage, scheduler, etc. 
The eventual goal of Global Scheduler is to support 100K clusters with a single cross-AZ control plane.

### Intelligent Scheduling Algorithm

Global Scheduler implements a multi-dimension optimization model based scheduling algorithm. 

### Application Aware Scheduling

The Global Scheduler Monitors each application’s input flow characteristics and automatically scale out/in
VMs/Containers or migrate the hosting VMs/Containers to a better geo-location to meet the application QOS requirement


## Build Global Scheduler


To build Global Scheduler, you just need to clone the repo and run "make":

##### Note: you need to have a working [Go 1.12 environment](https://golang.org/doc/install). Go 1.13 is not supported yet.

```
mkdir -p $GOPATH/src/github.com
cd $GOPATH/src/github.com
git clone https://github.com/futurewei-cloud/global-scheduler
cd global-scheduler
make
```

## Run Global Scheduler

To run a single-node Global Scheduler cluster in your local development box:

```
cd $GOPATH/src/github.com/global-scheduler
hack/global-scheduler-up.sh
```

## Documents and Support

The [design document folder](https://github.com/futurewei-cloud/global-scheduler/tree/master/docs/design-proposals/) contains the detailed design of already implemented features, and also some thoughts for planned features.

The [user guide folder](https://github.com/futurewei-cloud/global-scheduler/tree/master/docs/user-guide/) provides information about these features from users' perspective.

To report a problem, please [create an issue](https://github.com/futurewei-cloud/global-scheduler/issues) in the project repo. 

To ask a question, here is [the invitation](https://join.slack.com/t/arktosworkspace/shared_invite/zt-cmak5gjq-rBxX4vX2TGMyNeU~jzAMLQ) to join [Arktos slack channels](http://arktosworkspace.slack.com/). You can also post in the [email group](https://groups.google.com/forum/#!forum/arktos-user), or [create an issue](https://github.com/futurewei-cloud/arktos/issues) of question type in the repo.
