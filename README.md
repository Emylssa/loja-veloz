# 🚀 Loja Veloz — Plataforma de Microserviços com DevOps e Kubernetes

Projeto desenvolvido para demonstrar a aplicação prática de conceitos modernos de **DevOps**, **arquitetura de microserviços**, **conteinerização** e **orquestração com Kubernetes**.

O sistema simula uma plataforma de e-commerce composta por múltiplos serviços independentes, com pipeline automatizado de CI/CD e deploy em ambiente Kubernetes local.

---

# 📌 Arquitetura do Sistema

O sistema é composto pelos seguintes microserviços:

* 🛒 **Pedidos** — Gerenciamento de pedidos
* 📦 **Estoque** — Controle de produtos e inventário
* 💳 **Pagamentos** — Processamento de pagamentos
* 🌐 **Gateway** — API Gateway para acesso unificado

Cada serviço é executado de forma independente, permitindo escalabilidade e deploy isolado.

---

# 🏗️ Arquitetura Geral

```
Cliente → Gateway → Serviços Internos
                     ├── Pedidos
                     ├── Estoque
                     └── Pagamentos
```

---

# 🐳 Tecnologias Utilizadas

* Node.js
* Docker
* Docker Compose
* Kubernetes
* GitHub Actions (CI/CD)
* DockerHub (Registry de imagens)

---

# ⚙️ Execução do Projeto — Ambiente Local (Docker Compose)

## Pré-requisitos

* Docker Desktop instalado
* Docker Compose habilitado

## Subir todos os serviços

```bash
docker-compose up --build
```

O ambiente será iniciado automaticamente com todos os microserviços conectados.

---

# ☸️ Execução no Kubernetes

Este projeto possui manifests organizados na pasta:

```
k8s/
```

## Pré-requisitos

* Docker Desktop com Kubernetes habilitado
* kubectl instalado

## Aplicar recursos

```bash
kubectl apply -f k8s/
```

## Verificar pods

```bash
kubectl get pods
```

## Verificar serviços

```bash
kubectl get svc
```

---

# 🌐 Acesso ao Sistema

Após subir o ambiente Kubernetes, utilize o port-forward:

```bash
kubectl port-forward service/gateway 8080:80
```

Acesse no navegador:

```
http://localhost:8080
```

Resposta esperada:

```json
{"service":"service","status":"ok"}
```

---

# 🔄 Pipeline CI/CD

O projeto possui pipeline automatizado utilizando GitHub Actions que executa:

* Build das imagens Docker
* Publicação no DockerHub
* Versionamento automatizado
* Deploy automatizado (conceitual)

Secrets são armazenados de forma segura no repositório.

---

# 📦 Conteinerização

Cada microserviço possui:

* Dockerfile independente
* Imagens versionadas
* Configuração otimizada de dependências

As imagens são publicadas em:

```
docker.io/emylssa/*
```

---

# ☸️ Kubernetes — Recursos Utilizados

O ambiente Kubernetes inclui:

* Deployments
* Services (ClusterIP)
* ConfigMaps
* Secrets
* Múltiplos pods (alta disponibilidade)

Estratégia de deploy utilizada:

> Rolling Update (padrão Kubernetes)

---

# 📊 Observabilidade (Proposta)

O projeto prevê integração futura com ferramentas como:

* Prometheus (métricas)
* Grafana (dashboards)
* ELK Stack (logs)
* Jaeger (tracing distribuído)

---

# 📈 Escalabilidade

O Kubernetes permite:

* Escalonamento horizontal de pods
* Balanceamento automático de carga
* Alta disponibilidade entre réplicas

Pode ser aplicado HPA (Horizontal Pod Autoscaler) conforme necessidade.

---

# 🔐 Segurança

Boas práticas adotadas:

* Separação de configurações via ConfigMaps e Secrets
* Containers isolados
* Comunicação interna por rede Kubernetes

---

# 🎯 Objetivo Acadêmico

Demonstrar domínio prático em:

* Arquitetura de microserviços
* Conteinerização com Docker
* Orquestração com Kubernetes
* Automação com CI/CD
* Conceitos de observabilidade e escalabilidade

---

# 👩‍💻 Autora

**Emily da Silva Lessa**

Projeto desenvolvido para fins acadêmicos na disciplina de Cloud DevOps: Orchestrating Containers and Micro Services.

---

# 📄 Licença

Uso acadêmico.
