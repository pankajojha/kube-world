
minikube start --cpus 4 --memory 8096 --disk-size=40g


# kube-worl

export KUBEFLOW_SRC = ~/kube_flow_src

mkdir ${KUBEFLOW_SRC}
cd ${KUBEFLOW_SRC}
export KUBEFLOW_TAG=v0.4.1

curl https://raw.githubusercontent.com/kubeflow/kubeflow/${KUBEFLOW_TAG}/scripts/download.sh | bash

KUBEFLOW_REPO=${KUBEFLOW_SRC} ${KUBEFLOW_SRC}/scripts/kfctl.sh init ${KFAPP} --platform minikube
cd ${KFAPP}
${KUBEFLOW_SRC}/scripts/kfctl.sh generate all
${KUBEFLOW_SRC}/scripts/kfctl.sh apply all



