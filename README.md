# BOSH release for simple-go-web-app

This BOSH release and deployment manifest deploy a cluster of simple-go-web-app.

## Usage

This repository includes base manifests and operator files. They can be used for initial deployments and subsequently used for updating your deployments:

```
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=simple-go-web-app
git clone https://github.com/cloudfoundry-community/simple-go-web-app-boshrelease.git
bosh deploy simple-go-web-app-boshrelease/manifests/simple-go-web-app.yml
```

If your BOSH does not have Credhub/Config Server, then remember `--vars-store` to allow generation of passwords and certificates.

### Update

When new versions of `simple-go-web-app-boshrelease` are released the `manifests/simple-go-web-app.yml` file will be updated. This means you can easily `git pull` and `bosh deploy` to upgrade.

```
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=simple-go-web-app
cd simple-go-web-app-boshrelease
git pull
cd -
bosh deploy simple-go-web-app-boshrelease/manifests/simple-go-web-app.yml
```
