#wget https://gitlab.com/charts/gitlab-runner/raw/master/values.yaml
# https://docs.gitlab.com/runner/install/kubernetes.html
kubectl --namespace gitlab-managed-apps create secret generic gitlab-k8scloud-cert --from-file=gitlab.aliyun.k8scloud.site.crt
helm repo add gitlab https://charts.gitlab.io
helm install --namespace  gitlab-managed-apps --name gitlab-runner -f values.yaml gitlab/gitlab-runner
helm install --namespace  gitlab-managed-apps --name gitlab-runner2 -f values.yaml gitlab/gitlab-runner
helm upgrade --namespace  gitlab-managed-apps -f values.yaml gitlab-runner gitlab/gitlab-runner
