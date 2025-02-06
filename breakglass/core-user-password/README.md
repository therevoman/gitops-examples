# Set core user password 
This is a set of scripts to set a known password for the 'core' user on a set of OpenShift machines.

To use this script first replace the password, then apply the MachineConfig CR's using kustomize.

### First generate a new password
```
openssl passwd -6
```
### Then update the passwordHash in the patch yaml and update kustomization.yaml to include the files you want to modify
### Finally run the kustomize to apply the change to your cluster.
```
oc -k breakglass/core-user-password
```
