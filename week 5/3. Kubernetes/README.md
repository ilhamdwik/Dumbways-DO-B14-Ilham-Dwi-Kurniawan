# Task Microservices : Kubernetes

## leader - 2 CPU, 2GB RAM, 20GB Storage

![00](assets/0.png)


## 1. Deploy minikube dengan 2 node (1 control-plane, 1 worker)

* #### Pertama install minikube dan kubectl.
![01](assets/install_minikube_dan_kubectl/1.png)

* #### Disini ada error driver tidak terdeteksi. Sebelum menginstall minikube pastikan kalian sudah menginstall docker di dalam servernya, karena minikube membutuhkan docker untuk dijalankan sebagai driver.
![02](assets/install_minikube_dan_kubectl/2.png)

* #### Setelah diinstall docker baru bisa menjalankan minikube start.
![03](assets/install_minikube_dan_kubectl/3.png)

* #### Install kubectl. Disini saya menginstall kubectl menggunakan ansible-playbook.
![04](assets/install_minikube_dan_kubectl/4.png)
![05](assets/install_minikube_dan_kubectl/5.png)
![06](assets/install_minikube_dan_kubectl/6.png)
![07](assets/install_minikube_dan_kubectl/7.png)

* #### Selanjutnya cek bahwa kubectl sudah terinstall.
![08](assets/install_minikube_dan_kubectl/8.png)

### Catatan : karena saya disini ingin menjalankan multi-node didalam minikube maka ikuti langkah-langkah berikut.

* #### Jalankan perintah berikut untuk menjalankan 2 node di dalam minikube. Node 1 sebagai control-paneldan node 2 sebagai worker.
```
minikube start --nodes 2 -p multinode-ilham
```
![09](assets/task_kubernetes/1.png)

* #### Lalu cek.
```
kubectl get all

kubectl get nodes
```
![10](assets/task_kubernetes/2.png)


## 2. Deploy image nginx lalu expose menggunakan NodePort

* #### Create deployment nginx lalu expose portnya.
```
kubectl create deployment nginx --image=nginx
kubectl expose deployment nginx --type=NodePort --port=80
```
![11](assets/task_kubernetes/3.png)

* #### Untuk bisa diakses melalui localhost jalankan perintah berikut.
```
kubectl port-forward service/nginx 3001:80
```
![12](assets/task_kubernetes/4.png)


## 3. nginx bisa diakses langsung

* #### Untuk mengecek apakah sudah berhasil. Di server local kalian ssh ke dalam server yang menjalankan minikube. Lalu cek menggunakan curl apakah nginx sudah berjalan di port yang 3001, jika muncul script seperti gambar di bawah ini berarti nginx sudah berhasil dijalankan di localhost server menggunakan minikube.
```
curl 12.0.0.1:3001
```
![13](assets/task_kubernetes/5.png)


## Challenge

### - no 2 diganti deploy mongoDB lalu ping database sampai berhasil

* #### Untuk deploy mongodb di minikube sama seperti deploy nginx. Disini saya menggunakan image dari bitnami-mongodb.
```
kubectl create deployment mongodb --image=bitnami-mongodb
kubectl expose deployment mongodb --type=NodePort --port=27017
```
![14](assets/task_kubernetes/6.png)

* #### Port 27017 adalah default port dari mongodb, sedangkan 27200 adalah kita ingin menjalankan mongodb di server kita dengan port 27200.
```
kubectl port-forward service/[nama_service] 27200:27017
```
![15](assets/task_kubernetes/7.png)


### - gunakan ingress & replicaset