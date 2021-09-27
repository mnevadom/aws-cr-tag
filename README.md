# CR BUILD Action IBMCloud

This action is to build an image into AWS Cloud

## Entradas

### `url`

**Mandatory** url of the server like: XXXXXXXX.dkr.ecr.eu-west-3.amazonaws.com

### `namespacetag`

**Mandatory** namspacetag to build the image

### `namespace`

**Mandatory** namspace to build the image

### `imagename`

**Mandatory** image name

### `buildnr`

**Mandatory** build nr: typically commit nr

### `tag`

**Mandatory** new tag


## Ejemplo de uso

docker build -t ibm-cr-tag .
docker run -ti ibm-cr-tag XXXX.dkr.ecr.eu-west-3.amazonaws.com dgp-tag dgp-reg postservice 1.5.5

```yaml
# File: .github/workflows/workflow.yml
on: [push]

name: example

jobs:

  devflow:
    runs-on: ubuntu-latest
    steps:
    
    - uses: mnevadom/aws-cr-tag@v1
      with:
        url: 500664183679.dkr.ecr.eu-west-3.amazonaws.com
        namespace: dgp-reg
        imagename: postservice
        buildnr: c76d5f032667da9326bb8df7e96f06a4e3362044
        tag: 1.5.5

```
