# Выполнено ДЗ №1 Знакомство с решениями для запуска локального Kubernetes кластера, создание первого pod

 - [x] Основное ДЗ
 - [ ] Задание со *

## В процессе сделано:
 - Установлен minikube
 - Создал манифест namespace.yaml для namespace с именем homework
 - Создал манифест pod.yaml для создания pod

## Как запустить проект:
 - Применям манифесты
```
   kubectl apply -f namespace.yaml
   kubectl apply -f pod.yaml
```
## Как проверить работоспособность:
```
 kubectl get namespaces - проверям наличие нашего namespace
 kubectl get po -n homework -owide - проверяем наличие pod в нашем namespace  
 (или kubectl get po --all-namespaces)
```
## PR checklist:
 - [ ] Выставлен label с темой домашнего задания