## Problem

When `transformers` is used,
and the helm value is cert-folded,
as below

```
  FOO: |
    -----BEGIN CERTIFICATE-----
    FOO
    -----END CERTIFICATE-----
```

`helmfile` will raise an exception

```
err: [processing all.patched.yaml: parsing yaml doc from "    FOO\n    -----END CERTIFICATE--": yaml: unmarshal errors:
  line 1: cannot unmarshal !!str `FOO ---...` into chartify.res]
in ./helmfile.yaml: [processing all.patched.yaml: parsing yaml doc from "    FOO\n    -----END CERTIFICATE--": yaml: unmarshal errors:
  line 1: cannot unmarshal !!str `FOO ---...` into chartify.res]
```
