# A sample project to test workflow

The project is used to expiriment with workflow build process and how to
apply them on a cluster to served by the SoantaFlow operator without the
need to build the image by the operator itself.

To build the image:
```
podman build --ulimit nofile=5000:5000 -f workflow-builder.Dockerfile . -t quay.io/masayag/serverless-workflow-greeting
```

and to make it available for the operarot, either push to quay.io or to a local image registry:
```
podman push quay.io/masayag/serverless-workflow-greeting:latest
```

The image is referred by the generated and updated SoantaFlow CR under the manifests folder.
