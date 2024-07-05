
# Kubernetes Training Requirement

Brainmatics's Kubernetes Advance Training Software Requirement

## Software yang diperlukan

- WSL
- Docker desktop
- Minikube

## Install WSL

Docker Desktop memerlukan WSL untuk bisa dijalankan di Windows, untuk menginstallnya jalankan perintah berikut pada Windows Terminal

```powershell
wsl --install
```

## Prosedur pasca install WSL

- Restart Windows

## Install Docker Desktop

Jalankan perintah berikut pada Windows Terminal

```powershell
winget install --id Docker.DockerDesktop
```

## Prosedur pasca install Docker Desktop

- Buka Docker Desktop
- Klik ikon setting yang terdapat pada bagian window aplikasi
- Klik `Kubernetes` pada sidebar sebelah kiri
- Centang `Enable Kubernetes`
- Klik `Apply & Restart` pada bagian bawah

# Install Minikube

Jalankan perintah berikut pada Windows Terminal

```powershell
winget install --id Kubernetes.minikube
```

## Prosedur pasca install Minikube

Jalankan perintah berikut pada Windows Terminal

```powershell
minikube start
```

## Test instalasi

Pada Windows Terminal, jalankan perintah berikut

```powershell
kubectl run hello-kube --image=fhsinchy/hello-kube --port=80
kubectl get pod
kubectl expose pod hello-kube --type=LoadBalancer --port=80
kubectl get service
minikube service hello-kube
```

Jika berhasil, perintah di atas akan membuka browser mengakses aplikasi yang berjalan pada Kubernetes

Klik Ctrl+C untuk menghentikan aplikasi

Jalankan perintah berikut untuk menghapus aplikasi tersebut

```powershell
kubectl delete pod hello-kube
```

## Troubleshoot

Jika mengalami error `Unable to resolve the current Docker CLI context "default": context "default": context not found` ketika menjalankan minikube, jalankan perintah berikut pada Windows Terminal

```powershell
cd C:\Users\{WINDOWS_USER}\.docker\contexts\meta\
mkdir 37a8eec1ce19687d132fe29051dca629d164e2c4958ba141d5f4133a33f0688f
cp fe9c6bd7a66301f49ca9b6a70b217107cd1284598bfc254700c989b916da791e\meta.json .\37a8eec1ce19687d132fe29051dca629d164e2c4958ba141d5f4133a33f0688f\
```

Ganti `WINDOWS_USER` dengan Windows User yang sebenarnya

## Tambahan

Berdasarkan pengalaman menjadi asisten Training seperti ini, trainer sering mengupload hasil praktek ke GitLab, maka sekalian kita install Git

Jalankan perintah berikut pada Windows Terminal untuk menginstall Git

```powershell
winget install --id Git.Git
```
