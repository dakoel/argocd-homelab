# argocd

## Create a SealedSecret

1. Create a YAML file defining the Secret with the desired key-value-pairs (see template below)
2. Copy the output of `kubeseal --format yaml < <PATH_TO_SECRET_YAML>` to a suitable location within this repository
3. Customize the desired application(s) to use the new SealedSecret
4. Push & Sync

### Secret template

```yaml
---
apiVersion: v1
kind: Secret
metadata:
  name: <SECRET_NAME>
  namespace: <NAMESPACE>
type: Opaque
stringData:
  <KEY_1>: <VALUE_1>
  <KEY_2>: <VALUE_2>
```
