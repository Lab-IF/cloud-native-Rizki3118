# Praktikum Cloud-Native Application Development

**Kode Mata Kuliah:** CW6552021552  
**Semester:** V (Lima)  
**SKS:** 3 SKS  
**Program Studi:** Informatika  
**Fakultas:** Teknik  
**Universitas:** Muhammadiyah Makassar

---

## 📘 Deskripsi

Mata kuliah ini memperkenalkan prinsip-prinsip inti arsitektur cloud-native. Mahasiswa akan belajar cara mengemas aplikasi menggunakan kontainerisasi (Docker), mengelola kontainer dalam skala besar dengan orkestrasi (Kubernetes), dan memahami konsep infrastruktur yang tidak dapat diubah (immutable infrastructure).

## 🎯 Capaian Pembelajaran

Setelah menyelesaikan mata kuliah ini, mahasiswa diharapkan mampu:

1. Memahami prinsip cloud-native architecture
2. Menguasai containerization dengan Docker
3. Mampu melakukan container orchestration dengan Kubernetes
4. Mengimplementasikan microservices pattern
5. Menerapkan best practices cloud-native deployment

## 📚 Struktur Materi

Repositori ini mencakup materi untuk **8 pertemuan pertama** (sampai UTS):

| Pertemuan | Topik | Teknologi Utama |
|-----------|-------|-----------------|
| [01](./pertemuan-01) | **Introduction to Cloud-Native Principles** | 12-Factor App, Microservices |
| [02](./pertemuan-02) | **Docker Fundamentals: Images & Containers** | Docker CLI, Images, Containers |
| [03](./pertemuan-03) | **Dockerfile Best Practices** | Multi-stage builds, Optimization |
| [04](./pertemuan-04) | **Docker Compose untuk Multi-Container Apps** | docker-compose.yml, Networking |
| [05](./pertemuan-05) | **Container Registry** | Docker Hub, Private Registry |
| [06](./pertemuan-06) | **Kubernetes Architecture & Concepts** | Minikube, kubectl, Pods |
| [07](./pertemuan-07) | **Pods, Deployments, dan Services** | Deployments, Services, Scaling |
| [08](./pertemuan-08) | **UTS: Containerized Application** | Full-stack deployment project |

## 🚀 Getting Started

### Prerequisites

**Required Software:**
- Docker Desktop atau Docker Engine
- Docker Compose
- kubectl (Kubernetes CLI)
- Minikube (untuk local Kubernetes)
- Git
- Code Editor (VS Code recommended)

**System Requirements:**
- CPU: 4 cores (8 recommended)
- RAM: 8GB minimum (16GB recommended)
- Disk: 50GB free space
- OS: Linux, macOS, or Windows 10/11 with WSL2

### Quick Installation

#### Windows (with WSL2)
```powershell
# Install WSL2
wsl --install

# Install Docker Desktop
# Download from: https://www.docker.com/products/docker-desktop

# Install kubectl
choco install kubernetes-cli

# Install Minikube
choco install minikube
```

#### macOS
```bash
# Install Docker Desktop
brew install --cask docker

# Install kubectl
brew install kubectl

# Install Minikube
brew install minikube
```

#### Linux
```bash
# Install Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

# Install Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

### Verification

```bash
# Verify installations
docker --version
docker-compose --version
kubectl version --client
minikube version

# Start Minikube
minikube start --cpus=2 --memory=4096

# Verify Kubernetes
kubectl cluster-info
kubectl get nodes
```

## 📖 Cara Menggunakan Repository

### Untuk Setiap Pertemuan:

1. **Baca README.md** di folder pertemuan
2. **Setup environment** sesuai instruksi
3. **Ikuti tutorial** hands-on
4. **Praktikkan** semua examples
5. **Kerjakan tugas** yang diberikan
6. **Submit** hasil ke LMS

### Struktur Folder:

```
cloud-native-practicum/
├── README.md
├── examples/
│   ├── docker-samples/
│   ├── k8s-manifests/
│   └── compose-files/
├── pertemuan-01/
│   ├── README.md
│   └── exercises/
├── pertemuan-02/
│   └── ...
└── pertemuan-08/
    └── README.md (UTS Guidelines)
```

## 💻 Teknologi Stack

### Containerization
- **Docker**: Container runtime
- **Docker Compose**: Multi-container orchestration
- **Buildah/Podman**: Alternative container tools

### Orchestration
- **Kubernetes**: Container orchestration
- **Minikube**: Local Kubernetes
- **kubectl**: Kubernetes CLI
- **Helm**: Package manager (advanced)

### Development Tools
- **Visual Studio Code**: IDE
- **Docker Extension**: Container management
- **Kubernetes Extension**: K8s resources
- **Git**: Version control

### Cloud Platforms (Optional)
- **AWS**: EKS (Elastic Kubernetes Service)
- **Google Cloud**: GKE (Google Kubernetes Engine)
- **Azure**: AKS (Azure Kubernetes Service)
- **DigitalOcean**: DOKS (DigitalOcean Kubernetes)

## 📊 Sistem Penilaian

| Komponen | Bobot |
|----------|-------|
| Kehadiran & Partisipasi | 10% |
| Tugas Mingguan (Weekly Labs) | 30% |
| UTS (Mid-term Project) | 25% |
| UAS (Final Project & Presentation) | 35% |
| **TOTAL** | **100%** |

### Kriteria Kelulusan:
- Nilai akhir minimal: **60 (D)**
- Kehadiran minimal: **75%**
- Mengumpulkan minimal **75%** tugas
- Mengikuti UTS dan UAS

## 📝 Submission Guidelines

### Format File:
```
NIM_Nama_PertemuanXX/
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
├── kubernetes/
│   ├── deployment.yaml
│   └── service.yaml
├── src/
│   └── application-code/
├── docs/
│   └── README.md
└── screenshots/
```

### Checklist:
- [ ] Code bisa di-run tanpa error
- [ ] Dockerfile optimized
- [ ] Documentation lengkap
- [ ] Screenshots included
- [ ] Best practices applied
- [ ] Health checks implemented

## 🔧 Troubleshooting

### Docker Issues

**Docker daemon not running:**
```bash
# Linux
sudo systemctl start docker

# Windows/Mac
# Start Docker Desktop application
```

**Permission denied:**
```bash
# Linux - add user to docker group
sudo usermod -aG docker $USER
# Logout and login again
```

**Port already in use:**
```bash
# Find process using port
sudo lsof -i :8080

# Kill process
kill -9 <PID>
```

### Kubernetes Issues

**Minikube won't start:**
```bash
# Delete and recreate
minikube delete
minikube start --cpus=2 --memory=4096

# Check system resources
minikube status
```

**Pod stuck in Pending:**
```bash
# Describe pod for errors
kubectl describe pod <pod-name>

# Check node resources
kubectl describe node
```

**ImagePullBackOff error:**
```bash
# Check image name and tag
kubectl describe pod <pod-name>

# Pull image manually
docker pull <image-name>
```

## 📚 Resources

### Official Documentation:
- [Docker Documentation](https://docs.docker.com/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)

### Learning Resources:
- [Docker Getting Started](https://docs.docker.com/get-started/)
- [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [Play with Docker](https://labs.play-with-docker.com/)
- [Katacoda Interactive Learning](https://www.katacoda.com/)

### Books:
- "Docker Deep Dive" by Nigel Poulton
- "Kubernetes Up & Running" by Kelsey Hightower
- "Cloud Native DevOps with Kubernetes" by John Arundel

### Communities:
- [Docker Community](https://www.docker.com/community/)
- [Kubernetes Slack](https://kubernetes.slack.com/)
- [CNCF Community](https://www.cncf.io/community/)

## 💡 Best Practices

### Docker Best Practices:
1. Use official base images
2. Minimize layer count
3. Use multi-stage builds
4. Don't run as root
5. Use .dockerignore
6. Implement health checks
7. Keep images small
8. Version your images

### Kubernetes Best Practices:
1. Use namespaces
2. Set resource limits
3. Implement readiness/liveness probes
4. Use ConfigMaps and Secrets
5. Label everything
6. Use rolling updates
7. Implement monitoring
8. Plan for failures

### Cloud-Native Principles:
1. **Design for failure**
2. **Automate everything**
3. **Treat logs as streams**
4. **Keep it stateless**
5. **Use declarative configs**
6. **Implement observability**
7. **Secure by default**
8. **Scale horizontally**

## 👥 Tim Pengajar

**Dosen Pengampu:**  
[Nama Dosen]

**Asisten Praktikum:**  
[Nama Asisten]

## 📧 Kontak & Support

- **Email:** [email dosen/asisten]
- **Office Hours:** [jadwal konsultasi]
- **Discord/Slack:** [link workspace]

## 📄 Lisensi

Materi ini dibuat untuk keperluan pendidikan di Universitas Muhammadiyah Makassar.

---

## 🎓 Cloud-Native Mindset

**Key Principles to Remember:**

1. **Containers are ephemeral** - Design for disposability
2. **Configuration is external** - Use env vars and ConfigMaps
3. **Logs go to stdout** - Let the platform handle logging
4. **One process per container** - Keep containers focused
5. **Immutable infrastructure** - Replace, don't modify
6. **Declarative > Imperative** - Describe desired state
7. **Fail fast and loud** - Surface errors immediately
8. **Automate repetitive tasks** - Infrastructure as Code

---

## ⚠️ Important Notes

- **Docker Desktop** requires license for large enterprises
- **Minikube** is for development only, not production
- **Always backup** persistent data
- **Never commit secrets** to git
- **Test locally** before deploying
- **Monitor resource usage**
- **Keep images updated** for security

---

## 🚀 Let's Build Cloud-Native Apps!

Mulai dari [Pertemuan 01](./pertemuan-01) dan kuasai Docker dan Kubernetes!

**Welcome to the Cloud-Native World! ☁️🐳☸️**

---

**Last Updated:** December 2024  
**Version:** 1.0  
**Maintainer:** [Nama Asisten/Dosen]
