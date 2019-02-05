## Define a network for bosh deployments (non tiles)

```
./update-cloud-config.sh
```

For the convenience, this manifest uses the second half of `pas-services-network` for any bosh deployments (non tiles).
For a production environment, I'd highly recommend to have a dedicated network for non-tile deployments.

## Create an UAA client for credhub cli

`p-bosh` does not have an uaa client for credhub cli by default. 
To retrieve credentials from credhub, you need to create a client by manual.

See also [doc](https://community.pivotal.io/s/article/How-to-Access-CredHub-with-the-CredHub-CLI).

```
./uaac-token-client-get-p-bosh.sh
./uaac-create-client-credhub-cli.sh
```

Login to Credhub on `p-bosh`


```
./credhub-login.sh
```

## Deploy Concourse


```
./deploy-concourse.sh
```


Get the concourse admin password


```
credhub get -n /p-bosh/concourse/concourse_admin_password
```
