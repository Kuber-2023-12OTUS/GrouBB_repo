# Выполнено ДЗ №5

 - [х] Основное ДЗ
 - [х] Задание со *

## В процессе сделано:
В namespace homework создал service account monitoring и дать ему доступ к эндпоинту /metrics моего кластера
- Изменить манифест deployment из прошлых ДЗ так, чтобы поды запускались под service account monitoring
- В namespace homework создать service account с именем cd и дать ему роль admin в рамках namespace homework
- Создать kubeconfig для service account cd 
- Сгенерировать для service account cd токен с временем действия 1 день и сохранить его в файл token
## Как запустить проект:
 - Применяем манифесты
```
kubectl apply -f kubernetes-security/serviceaccount-monitoring.yaml
kubectl apply -f kubernetes-security/serviceaccount-cd.yaml
kubectl config view --minify --flatten > kubeconfig-cd
kubectl config set-credentials cd --token=<token>
kubectl config set-context cd --cluster=$(kubectl config view -o=jsonpath='{.clusters[0].name}') --user=cd
kubectl config use-context cd
Где <token> - это токен, который можно сгенерировать через API Kubernetes
```
Задание с *

Для задания с * необходимо настроить механизм вызова эндпоинта /metrics и сохранения ответа в файл metrics.html. 
Это может быть выполнено внутри контейнера вашего приложения в Deployment через скрипт, который вызывает нужный эндпоинт и сохраняет результат.
## Как проверить работоспособность:
```
kubectl get serviceaccount -n homework
kubectl get role -n homework
kubectl get rolebinding -n homework
kubectl get deployment -n homework

```

## PR checklist:
 - [ ] Выставлен label с темой домашнего задания
