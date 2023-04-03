# MLOps - Test Task ( Answers )

1. Install [Minikube](https://kubernetes.io/ru/docs/tasks/tools/install-minikube/#%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-minikube) and [kubectl](https://kubernetes.io/ru/docs/tasks/tools/install-kubectl/#%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-kubectl-%D0%B2-linux)
   * Or minikube official site
2. Dockerize `train.py`. Take into account that the container image. [Dockerfile](../app/Dockerfile)
4. Create and run Minikube cluster.
   * `minikube start`
5. Prepare kubectl configuration that:

- Create file `manifests/dockerconfig.json` that holds an authorization token to log in to Docker Hub.
```
kubectl create secret generic regcred \
    --from-file=.dockerconfigjson=manifests/dockerconfig.json \
    --type=kubernetes.io/dockerconfigjson
```

- `kubectl top pod POD_NAME --containers` - Show metrics for a given pod and its containers.\
  `kubectl top node my-node` - Show metrics for a given node.

- CMD [ "python", "./train.py" ]

- 