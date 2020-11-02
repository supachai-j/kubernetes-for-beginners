# เริ่มเรียนรู้ Kubernetes ด้วย minikube กัน
minikube เป็นเครื่องที่ช่วยในการติดตั้ง Kubernetes Cluster บนเครื่อง PC (Local) ทั้งระบบปฏิบัติการ macOS, Linux และ Windows โดยเครื่องมือสร้างขึ้นมาเพื่อช่วย developer ใช้พัฒนาโปรแกรมและสำหรับคนที่เริ่มทำการศึกษา Kubernetes ให้เรียนรู้ได้อย่างง่ายๆ 

## จุดเด่น
- รองรับ Kuernetes releases ใหม่ๆ เสมอ
- รองรับได้หลาย Platform (Linux, macOS, Windows)
- สามารถ Deploy บน VM, Container หรือ bare-metal
- รองรับ Container Runtime ได้หลายๆ ตัว (CRI-O, containerd, docker)
- รองรับ Docker API endpoint รองรับการ [push images](https://minikube.sigs.k8s.io/docs/handbook/pushing/#pushing-directly-to-the-in-cluster-docker-daemon) ได้ง่าย
- รองรับ advanced features เช่น LoadBalancer, filesystem moutns และ FeatureGates
- [Addons](https://minikube.sigs.k8s.io/docs/handbook/deploying/#addons) สำหรับการติดตั้ง Kubernetes applications ได้ง่าย

## เริ่มใข้งาน minikube
minikube เป็นการใช้งาน Kubernetes บน Local โดยการตั้งค่าที่ง่ายและเหมาะสำหรับการเรียนรู้ หรือสำหรับการพัฒนา application ต่างๆ บน Kubernetes 

ซึ่งในการติดตั้ง Kubernetes ปกติแล้วจะต้องมี Virtual Machine หรือ Docker ก่อน แต่สำหรับ minikube จะจัดการติดตั้งให้ทุกอย่าง เพียงใช้แค่คำสั่งเดียวคือ minikube start

## ต้องเตรียมอะไรไว้ก่อนบ้าง
- 2 CPUs  หรือมากกว่า
- 2GB free memory 
- 20GB free disk space
- internet connection
- Container หรือ Virtual Machine manager เช่น Docker, Hyperkit, Hyper-V, KVM, Parallels, Podman, VirtualBox หรือ VMWare.

## วิธีการติดตั้ง minikube

### 1. วิธีการติดตั้งบน macOS 
```
brew install minikube
```
ถ้าติดตั้งแล้วมีปัญหาลอง 
```
brew cask remove minikube
brew link minikube
```
### 2. ทำการติดตั้ง virtualbox บน macOS
```
brew install virtualbox
```
### 3. Start your cluster
ทำการเปิด Terminal ด้วย administrator access (แต่ไม่จำเป็นต้องใช้ root login), จากนั้นก็ใช้คำสั่ง
```
minikube start
```
ค่าเริ่มต้นจะใช้ driver ของ virtualbox แต่ถ้าต้องการใช้กับ VM Manager ตัวอื่นๆ ลองเข้าไปดูที่หน้า [Drivers](https://minikube.sigs.k8s.io/docs/drivers/) ที่รองรับการใช้งาน

หลังจากการติดตั้งและตั้งค่าต่างๆ เสร็จแล้ว ลองใช้คำสั่ง เพื่อดูค่าต่างๆ ผ่านคำสั่ง kubectl ดู
```
kubectl get node
```
บน minikube จะติดตั้งตัว Kubernetes Dashborad มาแล้ว
```
minikube dashboard
```
### 4. ทดสอบ Deploy Application
ลองทำการ deploy simple app และ expose บน port 8080
```
kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.4
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```
ลองดูรายการของ Services ของ hello-minikube
```
kubectl get services hello-minikube
```
เราสามารถใช้ minikube ในการเข้าถึง service ของ hello-minikube ได้โดยคำสั่งนี้ แล้วมันจะทำการเปิด web browser ขึ้นมาให้
```
minikube service hello-minikubes
```
หรืออีกทางคือใช้คำสั่งจาก kubectl สำหรับการ forward port ออกมาให้สามารถเรียกด้วย http://localhost:7080 ได้
```
kubectl port-forward service/hello-minikube 7080:8080
```
### 5. การจัดการ Kubernetes Cluster ด้วย minikube
ทำการ pause kubernetes 
```
minikube pause
```
ทำการปิด (Halt) Cluster
```
minikube stop
```
ทำการเพิ่ม memory limit (ต้องทำการ restart)
```
minikube config set memory 16384
```
ทำการลบ minikube cluster ทั้งหมด
```
minikube delete --all
```