# Persistent Volumes

- we create a Persistent volume
- then pods can request storage via Persistent volume claim request.
- 

## Dynamic provisioning
- PVC will automatically create a PV if one doesnt existing that matches the claim.

## Data
- you delete the Persistent volume your data is gone.

## Life cycle
- create a Persistent volume
- create a Persistent volume claim and refer the volume with how much size and attribute etc.
- then refer this Persistent volume claim in the deployment
