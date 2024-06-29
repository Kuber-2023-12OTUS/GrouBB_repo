# Выполнено ДЗ №2

 - [х] Основное ДЗ
 - [х] Задание со *

## В процессе сделано:
 - Использовался установленный minikube из ДЗ1 (namespace homework уже существует, namespace.yaml перенесен из первого ДЗ)
 - Назначена метка homework
 - Создан манифест deployment.yaml с реализацией задания со *

## Как запустить проект:
 - namespace уже существует по этому
 
Добавляем в для minikube label и применяем deployment.yaml
```
kubectl label nodes minikube homework=true
kubectl apply -f deployment.yaml
```
## Как проверить работоспособность:
```
kubectl get deployments -n homework
kubectl get pods -n homework
kubectl describe deployment homework-deployment -n homework
```

## PR checklist:
 - [ ] Выставлен label с темой домашнего задания
