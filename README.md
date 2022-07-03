# Homework
##HW1
- Добавлен манифест для web server
- Создан docker image для web server
- Создан docker image для hipster-frontend
- Добавлен манифест для hipster-frontend
- Добавлен исправленный рабочий манифест для hipster-frontend

###Команды для запуска
- kubectl apply -f web-pod.yaml
- kubectl apply -f frontend-pod-healthy.yaml
- kubectl port-forward --address 0.0.0.0 pod/web 8000:8000

###Проверка работоспособности
перейти по ссылке http://localhost:8000/homework.html, http://localhost:8000/index.html

##HW2
- Установлен кластер kind с использованием kind-config.yaml
- Добавлен манифест Replicaset frontend-replicaset.yaml
- Созданы и загружены Docker paymentservice версий 1.0 и 1.1
- Добавлен манифест Replicaset payment-replicaset.yaml
- Добавлен манифест Deployment payment-deployment.yaml
- Добавлены манифесты Deployment для реализации сценариев blue-green и Reverse Rolling Update через выставление параметров maxSurge и maxUnavailable
- Добавлен манифест Deployment frontend-deployment.yaml c Readiness Probe
- Добавлен манифест DaemonSet node-exporter-deamonset.yaml для развертывания Node Exporter

##Команды для запуска
- kubectl apply -f frontend-replicaset.yaml
- kubectl apply -f paymentservice-replicaset.yaml
- kubectl apply -f paymentservice-deployment.yaml
- kubectl apply -f paymentservice-deployment-bg.yaml
- kubectl apply -f paymentservice-deployment-reverse.yaml
- kubectl apply -f frontend-deployment.yaml
- kubectl apply -f node-exporter-daemonset.yaml

###Проверка работоспособности
- kubectl port-forward -n monitoring 9100:9100
- curl localhost:9100/metrics

##HW3
###Task01
- Добавлен манифест ServiceAccount с ClusterRole
- Добавлен манифест ServiceAccount без доступа к кластеру
###Task02
- Добавлен манифест Namespace prometheus
- Добавлен манифест ServiceAccount carol в namespace prometheus
- Добавлен манифест ClusterRole
- Добавлен манифест ClusterRoleBinding для ServiceAccount carol
###Task03
- Добавлен манифест Namespace dev
- Добавлен манифест ServiceAccount jane в namespace dev
- Добавлен манифест ClusterRoleBinding для ServiceAccount jane
- Добавлен манифест ServiceAccount ken в namespace dev
- Добавлен манифест ClusterRoleBinding для ServiceAccount ken

##Команды для запуска
- kubectl get ns
- kubectl get sa -n dev
- kubectl get rolebinding -n dev
- kubectl get clusterolebinding