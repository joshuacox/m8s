## [values.yaml](../m8s/values.yaml) Config

You can easily swap out your image by altering these lines:
[image settings](../m8s/values.yaml#L5-L7)

And the external host using these lines:
[host setting](../m8s/values.yaml#L17-L18)

These values can be overridden on the command line usingi the `--set` and
`--values` flags for helm, more info
[here](https://docs.helm.sh/helm/#helm-install)
and [here](https://docs.helm.sh/using_helm/#using-helm)
