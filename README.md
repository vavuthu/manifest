# Manifest file for RHEL7 pod

## Prerequisites
OCP cluster having secrets set to registry.redhat.io  
oc client  
Namespace "test" should exist with PodSecurity admission or If you want to run RHEL pod in different namespace,
modify the namespace [here](https://github.com/vavuthu/manifest/blob/master/rhel7.yaml#L6)

 
## Spinup RHEL7 pod
Download manifest file from https://raw.githubusercontent.com/vavuthu/manifest/master/rhel7.yaml
and run below command

```console
$ oc create -f rhel7.yaml 
pod/rhelpod created
```

check the status of pod
```console
$ oc get pod
NAME      READY   STATUS    RESTARTS   AGE
rhelpod   1/1     Running   0          47s
```

run command inside pod
```console
$ oc rsh rhelpod cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.9 (Maipo)
```

