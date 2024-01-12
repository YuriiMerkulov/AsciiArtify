Application deployment in ArgoCD

![](../img/argo.png)

1. Add port forwarding
```bash
k port-forward -n demo svc/ambassador 8088:80
```
2. Download any .png file
```bash
wget -O /tmp/u.png https://brandslogos.com/wp-content/uploads/images/ubuntu-logo.png
```
3. Upload the file to the converter
```bash
curl -F 'image=@/tmp/u.png' localhost:8088/img/
```

The result might be something like this:

![](../img/logo.png)
