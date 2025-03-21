# JupyterHub

## Disclaimer

This is not an official production ready code. It's meant to be used as a PoC.

## Overview

JupyterHub brings the power of notebooks to groups of users. It gives users access to computational environments and resources without burdening the users with installation and maintenance tasks.

## Access

- You can access JupyterHub using the application dashboard available on the cluster **Application Dashboards** tab
- Also accessible by using your NKP Dashboard URL with the path `/jupyter/`

### Credentials

- Username: admin
- Password: nutanix/4u

To overwrite the credentials, use the **Workspace Configuration** when enabling the application:

```yaml
hub:
  config:
    Authenticator:
      admin_users:
        - admin
    DummyAuthenticator:
      password: nutanix/4u
```

## More Information

- [jupyter.org](https://jupyter.org/hub)
- [Jupyter Documentation](https://docs.jupyter.org/en/latest/)
- [JupyterHub for Kubernetes](https://z2jh.jupyter.org/en/stable/)
- [List of Helm values](https://github.com/jupyterhub/zero-to-jupyterhub-k8s/blob/main/jupyterhub/values.yaml)
