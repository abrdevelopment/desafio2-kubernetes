# 🚀 Desafio 2 - Kubernetes DIO

![Kubernetes](https://upload.wikimedia.org/wikipedia/commons/3/39/Kubernetes_logo_without_workmark.svg)

> Projeto de estudo e prática com **Kubernetes**, utilizando **Kind** (Kubernetes in Docker) para orquestração de containers e deploy de aplicações.

[![CI/CD](https://github.com/abrdevelopment/desafio2-kubernetes/actions/workflows/deploy.yml/badge.svg)](https://github.com/abrdevelopment/desafio2-kubernetes/actions)

---

## 📂 Estrutura do Repositório
```bash
desafio2-kubernetes/
├── .github/workflows/ # Workflows de CI/CD
├── app/ # Código da aplicação (frontend/backend)
├── database/ # Configuração do banco de dados
└── k8s/ # Manifests Kubernetes (Deployments, Services, PV, PVC, etc.)
```

---

## 🛠️ Tecnologias Utilizadas

- **Kubernetes** (Kind)
- **Docker**
- **HTML / CSS / JavaScript**
- **PHP**
- **Apache HTTP Server**
- **MySQL**
- **GitHub Actions** (CI/CD)

---

## 📦 Pré-requisitos

Antes de começar, instale:

- [Docker](https://docs.docker.com/get-docker/)
- [Kind](https://kind.sigs.k8s.io/docs/user/quick-start/)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/)

---

## ▶️ Como Executar o Projeto

1. **Clonar o repositório**
   ```bash
   git clone https://github.com/abrdevelopment/desafio2-kubernetes.git
   cd desafio2-kubernetes

1. **Criar o cluster com Kind**
  ```bash
  kind create cluster --name desafio2
  ```
1. **Aplicar os manifests Kubernetes**
  ```bash
  kubectl apply -f k8s/
  ```
1. **Verificar recursos**
  ```bash
  kubectl get all
  ````
1. **Acessar a aplicação**
- Localize o Service exposto:
  ```bash
  kubectl get svc
  ```
Caso esteja usando NodePort, acesse http://localhost:porta

## 📌 Funcionalidades
- Deploy automatizado da aplicação e banco de dados no Kubernetes
- Uso de Persistent Volumes (PV) e Persistent Volume Claims (PVC)
- Configuração de Services para exposição interna e externa
- Integração com GitHub Actions para CI/CD

## 🗺️ Arquitetura do Cluster
  ```mermaid
  graph TD
  subgraph User
      A[💻 Usuário]
  end

  subgraph "K8s Cluster - Kind"
      B[🌐 Service - Frontend]
      C[📦 Pod - App PHP/Apache]
      D[🗄️ Pod - MySQL]
      E[(📂 Persistent Volume)]
  end

  A -->|HTTP Request| B
  B --> C
  C --> D
  D --> E
  ```

## 📚 Aprendizados
Este projeto reforça conceitos como:

- Estruturação de manifests Kubernetes
- Deploy de aplicações multi-container
- Persistência de dados com PV/PVC
- Exposição de serviços no cluster
- Automação de deploy com GitHub Actions

## 🤝 Contribuindo
- Faça um fork do projeto
- Crie uma branch para sua feature:
  ```bash
  git checkout -b minha-feature
  ```

- Commit suas alterações: 
  ```bash
  git commit -m 'Minha nova feature')
  ```

- Faça push para a branch:
  ```bash
  git push origin minha-feature
  ```

- Abra um Pull Request

## 📄 Licença
Este projeto está sob a licença MIT.


