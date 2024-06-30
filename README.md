# Выполнено ДЗ №3

 - [х] Основное ДЗ
 - [х] Задание со *

## В процессе сделано:
 - Использовался установленный minikube из ДЗ1 (namespace homework уже существует, namespace.yaml, deployment.yaml  перенесен из предыдущего ДЗ)
 - Изменил readiness-пробу в манифесте deployment.yaml
 - Установил в кластер ingress-контроллер nginx (добавил задание со *)
 - Созданы service.yaml, ingress.yaml 

## Как запустить проект:
 - Применяем манифесты
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
kubectl apply -f namespace.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
homework.otus в /etc/hosts
```
## Как проверить работоспособность:
Для проверки открыть в браузере http://homework.otus/index.html. 

## PR checklist:
 - [ ] Выставлен label с темой домашнего задания
