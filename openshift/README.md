### OpenShift Templates for Catalog and Inventory

These templates implement services for the lab.

To deploy catalog:

```
oc process -f catalog-template.yml GIT_URI=this_repo GIT_CONTEXT_DIR=catalog | oc create -f -
```

To deploy inventory v1 and v2 with a delay (and as many others as you want):

```
oc process -f inventory-svc-template.yml |oc create -f -
oc process -f inventory-deployment-template.yml SERVICE_VERSION=v1 |oc create -f -
oc process -f inventory-deployment-template.yml SERVICE_VERSION=v2 SERVICE_DELAY=2000 |oc create -f -
```

