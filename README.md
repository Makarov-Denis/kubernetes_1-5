# Домашнее задание к занятию "`Сетевое взаимодействие в K8S. Часть 2`" - `Макаров Денис`

---

## Задание 1. Создать Deployment приложений backend и frontend

Создаем namespace для нового задания:

![Uploading kubdz5.PNG…]()

### 1. Создать Deployment приложения _frontend_ из образа nginx с количеством реплик 3 шт.

![fronted](https://github.com/user-attachments/assets/7cc3b231-7eef-46ef-ac3f-6466590100fb)

### 2. Создать Deployment приложения _backend_ из образа multitool. 

![backend](https://github.com/user-attachments/assets/a8af9e96-9710-4d5c-8b96-04369e6aa6e4)

### 3. Добавить Service, которые обеспечат доступ к обоим приложениям внутри кластера. 
Поднимаем frontend:

![apply front](https://github.com/user-attachments/assets/a3cb38d1-245e-42f8-b356-84dee85a4b48)

![apply backend](https://github.com/user-attachments/assets/b8ca80d1-d4bf-43cf-933d-5488465ea712)

### 4. Продемонстрировать, что приложения видят друг друга с помощью Service.
Сначала с ПОДов frontend:

![curl front](https://github.com/user-attachments/assets/02ff335a-fd13-4bf4-8a77-ad7442496e29)

Теперь обратно:

![curl backend](https://github.com/user-attachments/assets/853a9713-108d-4812-a7bd-80bd3f5c3dbc)

### 5. Предоставить манифесты Deployment и Service в решении, а также скриншоты или вывод команды п.4.

------

## Задание 2. Создать Ingress и обеспечить доступ к приложениям снаружи кластера

### 1. Включить Ingress-controller в MicroK8S.

![microk8s status](https://github.com/user-attachments/assets/6fb4ca58-99c7-462b-8746-9b0549249a85)

![enable ingress](https://github.com/user-attachments/assets/b3e0c161-83be-4647-8df3-ed6b1fb01085)

Проверяем:

![microk8s status](https://github.com/user-attachments/assets/cdc028a3-7db4-496b-8c4c-cca628c8e0a4)

### 2. Создать Ingress, обеспечивающий доступ снаружи по IP-адресу кластера MicroK8S так, чтобы при запросе только по адресу открывался _frontend_ а при добавлении /api - _backend_.

![ingres](https://github.com/user-attachments/assets/1ebfa87d-86f3-4adf-8797-18d1d9843788)

Разворачиваем манифест ingress:

![ingress apply](https://github.com/user-attachments/assets/48033aeb-b2a2-4239-95b7-20551017b55d)

### 3. Продемонстрировать доступ с помощью браузера или `curl` с локального компьютера.

![curl cluster](https://github.com/user-attachments/assets/1f03637e-7087-4a41-ba7a-8f1171745fd5)

![site api](https://github.com/user-attachments/assets/776ead54-5e70-450e-bbac-bf2a4a293d39)

![site](https://github.com/user-attachments/assets/918bd263-9788-4e81-8af4-9fb3948c613e)


### 4. Предоставить манифесты и скриншоты или вывод команды п.2.


------
