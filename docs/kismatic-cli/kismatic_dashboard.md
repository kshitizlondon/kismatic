## kismatic dashboard

Opens the kubernetes dashboard URL of the cluster

### Synopsis


  This command is a convenience command to open the dashbord.
  - Retrieves the token of the secret for ServiceAccount 'kubernetes-dashboard-admin':
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  export SECRET="$(./kubectl get sa kubernetes-dashboard-admin -o 'jsonpath={.secrets[0].name}' -n kube-system --kubeconfig generated/kubeconfig)"
  ./kubectl describe secrets $SECRET -n kube-system --kubeconfig generated/kubeconfig | awk '$1=="token:"{print $2}'
  -----------------------------------------------------------------------------------------------------------------------------------------------------

  - Runs 'kubectl proxy':
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  kubectl proxy --kubeconfig generated/kubeconfig
  -----------------------------------------------------------------------------------------------------------------------------------------------------

```
kismatic dashboard [flags]
```

### Examples

```
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  ./kismatic dashboard
  Opening kubernetes dashboard in default browser...
  Use the kubeconfig in "generated/dashboard-admin-kubeconfig"
  Starting to serve on 127.0.0.1:8001
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  ./kismatic dashboard url
  http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/login
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  ./kismatic dashboard kubeconfig
  Generated kubeconfig in "generated/dashboard-admin-kubeconfig"
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  ./kismatic dashboard token
  eyJhbGciOiJSUzI1NiIsImtpZCI6IiJ9.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJrdWJlLXN5c3RlbSIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJrdWJlcm5ldGVzLWRhc2hib2FyZC1hZG1pbi10b2tlbi1kd2o1eiIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50Lm5hbWUiOiJrdWJlcm5ldGVzLWRhc2hib2FyZC1hZG1pbiIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50LnVpZCI6ImNjZGQyYmViLTZmMmUtMTFlOC1hNjM5LTBhMWQ1NzNmODZiOCIsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudDprdWJlLXN5c3RlbTprdWJlcm5ldGVzLWRhc2hib2FyZC1hZG1pbiJ9.VxrM2p3lJHFK9U7Zg6wTjHC-bGKOvkR31_8KIbveQyUjlP7xnlwKm6PKgS-mjyGyZEvBjEIO3xsY-8YEW-1n091fNnPCkBmJLxlljhfpPu9JzgsG1KOe6Ha1-aOHO4PsH8fZYVylOdIP13zo9v5kgmpE7j5YecKY-6aWzyB8tverNJoMN8kvCUsrzVcfV3uOGBsdcn1aDtSSyiKfb5UdIKVkB-4i9VDR3xgAmDP1hTM50aXT1chpt69E-4Cl4qBwYR4mj47V1aTh0oK10Qv6XHd4zydHahlbSiM7LHMjTVekEIooDHoQuqIe9vnzVoPHp-PRWrNetRCSfNJfsRBD7Q
  -----------------------------------------------------------------------------------------------------------------------------------------------------
```

### Options

```
      --generated-assets-dir string   path to the directory where assets generated during the installation process will be stored (default "generated")
  -h, --help                          help for dashboard
  -f, --plan-file string              path to the installation plan file (default "kismatic-cluster.yaml")
```

### SEE ALSO

* [kismatic](kismatic.md)	 - kismatic is the main tool for managing your Kubernetes cluster
* [kismatic dashboard kubeconfig](kismatic_dashboard_kubeconfig.md)	 - Generate a kubeconfig file with the ServiceAccount 'kubernetes-dashboard-admin' token
* [kismatic dashboard token](kismatic_dashboard_token.md)	 - Print the ServiceAccount 'kubernetes-dashboard-admin' token
* [kismatic dashboard url](kismatic_dashboard_url.md)	 - Display the kubernetes dashboard URL

###### Auto generated by spf13/cobra on 13-Jun-2018
