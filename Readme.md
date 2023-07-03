# sample-compositions-match-labels

```bash
NAME                                                           READY   SYNCED   EXTERNAL-NAME           AGE
routetable.ec2.aws.upbound.io/network-rtb-sample-hp4vb-glcz5   True    True     rtb-093ca591cf676c841   45s

NAME                                                READY   SYNCED   EXTERNAL-NAME           AGE
vpc.ec2.aws.upbound.io/network-sample-r6rfs-sw6lq   True    True     vpc-08893b290a8eb512f   10m
```

check for details managed-resource routetable:

```bash
apiVersion: ec2.aws.upbound.io/v1beta1
kind: RouteTable
metadata:
  annotations:
    crossplane.io/composition-resource-name: routetable
    crossplane.io/external-create-pending: "2023-07-03T10:20:53Z"
    crossplane.io/external-create-succeeded: "2023-07-03T10:20:53Z"
    crossplane.io/external-name: rtb-093ca591cf676c841
    upjet.crossplane.io/provider-meta: '{"e2bfb730-ecaa-11e6-8f88-34363bc7c4c0":{"create":300000000000,"delete":300000000000,"update":120000000000}}'
  creationTimestamp: "2023-07-03T10:20:52Z"
  finalizers:
  - finalizer.managedresource.crossplane.io
  generateName: network-rtb-sample-hp4vb-
  generation: 3
  labels:
    crossplane.io/claim-name: network-rtb-sample
    crossplane.io/claim-namespace: default
    crossplane.io/composite: network-rtb-sample-hp4vb
    name: my-rtb
    resource: routeTable
  name: network-rtb-sample-hp4vb-glcz5
  ownerReferences:
  - apiVersion: example.crossplane.io/v1alpha1
    blockOwnerDeletion: true
    controller: true
    kind: XNetworkRtbSample
    name: network-rtb-sample-hp4vb
    uid: 6acd6641-63b0-448b-9a64-89bf6d7dc7c6
  resourceVersion: "5179"
  uid: f3604133-3f78-49ea-9c2c-7f4794b44a61
spec:
  deletionPolicy: Delete
  forProvider:
    region: eu-central-1
    tags:
      crossplane-kind: routetable.ec2.aws.upbound.io
      crossplane-name: network-rtb-sample-hp4vb-glcz5
      crossplane-providerconfig: default
    vpcId: vpc-08893b290a8eb512f
    vpcIdRef:
      name: network-sample-r6rfs-sw6lq
    vpcIdSelector:
      matchLabels:
        name: my-vpc
        resource: vpc
  managementPolicy: FullControl
  providerConfigRef:
    name: default
status:
  atProvider:
    arn: arn:aws:ec2:eu-central-1:255932642927:route-table/rtb-093ca591cf676c841
    id: rtb-093ca591cf676c841
    ownerId: "255932642927"
    tags:
      crossplane-kind: routetable.ec2.aws.upbound.io
      crossplane-name: network-rtb-sample-hp4vb-glcz5
      crossplane-providerconfig: default
    tagsAll:
      crossplane-kind: routetable.ec2.aws.upbound.io
      crossplane-name: network-rtb-sample-hp4vb-glcz5
      crossplane-providerconfig: default
    vpcId: vpc-08893b290a8eb512f
  conditions:
  - lastTransitionTime: "2023-07-03T10:20:56Z"
    reason: Available
    status: "True"
    type: Ready
  - lastTransitionTime: "2023-07-03T10:20:53Z"
    reason: ReconcileSuccess
    status: "True"
    type: Synced
  - lastTransitionTime: "2023-07-03T10:20:54Z"
    reason: Success
    status: "True"
    type: LastAsyncOperation
  - lastTransitionTime: "2023-07-03T10:20:54Z"
    reason: Finished
    status: "True"
    type: AsyncOperation
```
