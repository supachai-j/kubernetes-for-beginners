# เริ่มเรียนรู้ Kubernetes ด้วย minikube กัน
minikube เป็นเครื่องที่ช่วยในการติดตั้ง Kubernetes Cluster บนเครื่อง PC (Local) ทั้งระบบปฏิบัติการ macOS, Linux และ Windows โดยเครื่องมือสร้างขึ้นมาเพื่อช่วย developer ใช้พัฒนาโปรแกรมและสำหรับคนที่เริ่มทำการศึกษา Kubernetes ให้เรียนรู้ได้อย่างง่ายๆ 

# จุดเด่น
- รองรับ Kuernetes ใหม่ๆ เสมอ
- รองรับได้หลาย Platform (Linux, macOS, Windows)
- สามารถ Deploy บน VM, Container หรือ bare-metal
- รองรับ Container Runtime ได้หลายๆ ตัว (CRI-O, containerd, docker)
- รองรับ Docker API endpoint รองรับการ [push images](https://minikube.sigs.k8s.io/docs/handbook/pushing/#pushing-directly-to-the-in-cluster-docker-daemon) ได้ง่าย
