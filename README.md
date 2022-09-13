# Wordpress template

Run wordpress on the Red Hat OpenShift platform. This package is based on [bitnami images](https://hub.docker.com/r/bitnami/wordpress).

## How to use this template

Install the template by downloading the [wordpress-template.yaml](./wordpress-template.yaml) file and import it to your OpenShift project via
command line. Download the `oc` client. Then:

```sh
oc login "openshift-address" --token="<TOKEN>"
oc new-project "<project-name>"
```

**NOTE:** Replace `<TOKEN>` by the corresponding value

Process and apply template using default values from the template and passing your application specific parameters.

```sh
oc process -f wordpress-template.yaml \
   -p NAME=<NAME> | oc apply -f -
```

**NOTE:** Replace `<NAME>` by the corresponding value. The name will be used to for the URL.

## Deleting the application

```sh
oc delete all,pvc -l app=wordpress
```
