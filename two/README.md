## Problem

When helm Chartname is different from the basename in `helmfile`,
there would be an exception:

```
in ./helmfile.yaml: [exit status 1

COMMAND:
  kustomize build /tmp/chartify1221228177/test --output /tmp/chartify1221228177/test/all.patched.yaml

OUTPUT:
  :: This is {Version:kustomize/v4.4.1 GitCommit:b2d65ddc98e09187a8e38adc27c30bab078c1dbf BuildDate:2021-11-11T23:36:27Z GoOs:linux GoArch:amd64}
  Error: accumulating resources: accumulation err='accumulating resources from 'helmx.1.rendered/chartName/templates/test.yaml': evalsymlink failure on '/tmp/chartify1221228177/test/helmx.1.rendered/chartName/templates/test.yaml' : lstat /tmp/chartify1221228177/test/helmx.1.rendered: no such file or directory': evalsymlink failure on '/tmp/chartify1221228177/test/helmx.1.rendered/chartName/templates/test.yaml' : lstat /tmp/chartify1221228177/test/helmx.1.rendered: no such file or directory]
```

## Bug

https://github.com/variantdev/chartify/pull/13
