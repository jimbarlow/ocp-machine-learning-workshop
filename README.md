## 01_odh.yml notes
https://github.com/aws-quickstart/quickstart-redhat-openshift/issues/238
```
# oc create sa postgres  -n userXX-notebooks
# oc adm policy add-scc-to-user privileged -z postgres -n userXX-notebooks
# oc apply -f 01_odh.yaml
# oc patch  dc jupyterhub-db -n userXX-notebooks  --type='json' -p='[{"op": "add", "path": "/spec/template/spec/serviceAccount", "value": "postgres" },{"op": "add", "path": "/spec/template/spec/serviceAccountName", "value": "postgres" }]'
```

