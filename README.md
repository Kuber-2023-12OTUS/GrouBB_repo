# Выполнено ДЗ №4

 - [х] Основное ДЗ
 - [ ] Задание со *

## В процессе сделано:
- Создал манифест pvc.yaml, описывающий PersistentVolumeClaim, запрашивающий хранилище с storageClass по-умолчанию
- Создал манифест cm.yaml для объекта типа configMap, описывающий произвольный набор пар ключ-значение
- В манифесте deployment.yaml изменил спецификацию volume типа emptyDir, который монтируется в init и основной контейнер, на pvc, созданный в предыдущем пункте
- В манифесте deployment.yaml добавил монтирование ранее созданного configMap как volume к основному контейнеру пода в директорию /homework/conf, так, чтобы его содержимое можно было получить, обратившись по url /conf/file 

## Как запустить проект:
 - Применяем манифесты
```
kubectl apply -f kubernetes-volumes/pvc.yaml
kubectl apply -f kubernetes-volumes/cm.yaml
kubectl apply -f kubernetes-volumes/storageClass.yaml
```
## Как проверить работоспособность:
```
kubectl get pvc -n homework
kubectl get cm -n homework
kubectl get deployment -n homework
```

## PR checklist:
 - [ ] Выставлен label с темой домашнего задания
