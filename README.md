# nkp-demo-catalog-applications

Disclaimer: This is not an official production ready code. It's meant to be used as a PoC.

## Overview

This demo catalog repository holds examples of applications to help understand how NKP custom catalog works.

## Prerequisites

- An NKP cluster with Ultimate license
- Internet connection
- NKP CLI installed
- kubectl installed

## How to add this catalog on your management cluster?

```shell
nkp create catalog nkp-demo-catalog-applications \
    -w kommander-workspace \
    --branch main \
    --url https://github.com/nutanixdev/nkp-demo-catalog-applications
```

## How to list all the catalogs on your management cluster?

```shell
kubectl get gitrepository -n kommander
```

## How to list all the apps provided by this catalog?

```shell
kubectl get apps -n kommander
```

## How to add this catalog to a different Workspace?

1. List your NKP Workspaces

    ```shell
    nkp get workspaces
    ```

    ```shell
    NAME                    NAMESPACE                   
    default-workspace       kommander-default-workspace
    hybrid-cloud            hybrid-cloud               
    kommander-workspace     kommander   
    ```

1. Run the following command using your Workspace name

    ```shell
    nkp create catalog nkp-demo-catalog-applications \
        -w  <workspace_name> \
        --branch main \
        --url https://github.com/nutanixdev/nkp-demo-catalog-applications
    ```

    Ex:

    ```shell
    nkp create catalog nkp-demo-catalog-applications \
        -w hybrid-cloud \
        --branch main \
        --url https://github.com/nutanixdev/nkp-demo-catalog-applications
    ```

## How to delete this catalog from a Workspace?

1. [List your NKP Workspaces](#how-to-add-this-catalog-to-a-different-workspace)

1. Run the following command using your Workspace **namespace**

    ```shell
    kubectl delete gitrepository nkp-demo-catalog-applications -n <workspace_namespace>
    ```

    Ex:

    ```shell
    kubectl delete gitrepository nkp-demo-catalog-applications -n hybrid-cloud
    ```

## Contributing

See the [contributing docs](CONTRIBUTING.md).

## Support

### Community Plus

This code is developed in the open with input from the community through issues and PRs. The Nutanix marketing team serves as the maintainer.

Issues and enhancement requests can be submitted in the [Issues tab of this repository](../../issues). Please search for and review the existing open issues before submitting a new issue.

## License

The project is released under version 2.0 of the [Apache license](http://www.apache.org/licenses/LICENSE-2.0).
