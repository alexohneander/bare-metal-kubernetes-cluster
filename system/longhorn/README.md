# Installation
```bash
ka longhorn.yml
```

## Create an Ingress with Basic Authentication
```bash
USER=<USERNAME_HERE>; PASSWORD=<PASSWORD_HERE>; echo "${USER}:$(openssl passwd -stdin -apr1 <<< ${PASSWORD})" >> auth
```
```bash
kubectl -n longhorn-system create secret generic basic-auth --from-file=auth
```

```bash
kubectl -n longhorn-system apply -f longhorn-ingress.yml
```