# Hello Docker (Spring Boot)
Aplicação Java 17 + Spring Boot 3 minimalista para demonstrar Dockerfile e docker-compose.

## Deploy na VM

### 1. Login na VM
```bash
ssh madjer@20.10.29.47
```

### 2. Atualizar sistema e baixar pacotes necessários
```bash
sudo dnf update
sudo dnf update -y
sudo dnf install -y yum-utils
```

### 3. Adicionar repositório Docker
```bash
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

### 4. Instalar Docker Engine
```bash
sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### 5. Conferir o status do Docker
```bash
sudo systemctl status docker
```

### 6. Liberar uso sem sudo
```bash
sudo usermod -aG docker madjer
newgrp docker
```

### 7. Iniciar docker
```bash
sudo systemctl enable --now docker
```

### 8. Testar a instalação
```bash
docker run hello-world
```

### 9. Instalar o Git
```bash
sudo dnf install -y git
git --version
```

### 10. Clonar o repositório
```bash
git clone https://github.com/MadjerFin/VitsApi
```

### 11. Buildar e rodar o projeto
```bash
cd VitsApi/
docker compose build
docker compose up -d
docker compose ps
```

### 12. Acessar o projeto
```
http://20.10.29.47/swagger-ui/index.html#/
```
