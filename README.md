This repo is a simple example intended to verify that kustomize functions in your environment, and give examples on how to configure overlays.

Requirements:
- Either kubectl version 1.14 or higher, or the kustomize binary.

Building
- building DEV yaml files:
```
kustomize build DEV` (or `kubectl kustomize DEV`)
```
- building PROD yaml files: 
```
kustomize build PROD (or kubectl kustomize PROD)
```

The output of the above command will go to standard output so you will likely want to redirect it to a file.

Files

BASE (directory with the base yaml):
- kustomization.yaml      Contains a list the yaml files to be kustomized.
- proxy-cm.yaml           Example config map to demo patching.
- tomcat-deployment.yaml  Example deployment to demo patching.


DEV (overlay files for dev):
- kustomization.yaml  Kustomization file for this overlay. See file commnents
- limits.yaml         Example patch file add limits to tomcat-deployment.yaml
- cm.yaml             Example patch file to patch HTTP_PROXY in proxy-cm.yaml.
- hosts               File used by configmap creation demo
- passwd              File used by secret creation demo


PROD (overlay files for prod:
- kustomization.yaml  Kustomization file for this overlay. See file commnents
- limits.yaml         Example patch file add limits to tomcat-deployment.yaml
- cm.yaml             Example patch file to patch HTTP_PROXY in proxy-cm.yaml.
- hosts               File used by configmap creation demo
- passwd              File used by secret creation demo
