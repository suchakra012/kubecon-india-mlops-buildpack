# kubecon-india-mlops-buildpack
Demo to be presented at KubeCon India on Buildpacks-MLOps

**Build Image Using Cloud Native Buildpack**
=====================
This repository has instruction to build image without Dockerfile for Simple Machine Learning Model in Python using scikit-learn using [Cloud Native Buildpack](https://buildpacks.io/).

Instruction

-------------------------------------------

* Clone repository `git clone https://github.com/suchakra012/kubecon-india-mlops-buildpack`.


* Build the image and publish to any OCI registry (used here is Docker Registry)

```sh
cd kubecon-india-mlops-buildpack
pack build docker.io/<user-repository-name>/ml-model-app:v1 --path . --builder  paketobuildpacks/builder-jammy-base --env "BP_CPYTHON_VERSION=3.11.9" --env "BP_ENABLE_RUNTIME_CERT_BINDING=false" --publish
```

* Run the container
```sh
docker run docker.io/<user-repository-name>/ml-model-app:v1
```
