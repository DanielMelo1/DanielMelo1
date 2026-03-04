# Daniel Melo

**Cloud Engineer** focado em **Kubernetes**, **DevSecOps** e **Observability** na AWS.

Construo infraestrutura que resolve problemas reais — não só tutoriais.  
Cada projeto aqui foi executado, testado, e tem evidência do que funcionou *e* do que não funcionou.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-danielaugustormelo-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com/in/danielaugustormelo)
[![Medium](https://img.shields.io/badge/Medium-@dreimao4-000000?style=flat-square&logo=medium)](https://medium.com/@dreimao4)
[![AWS](https://img.shields.io/badge/AWS-Cloud_Practitioner-FF9900?style=flat-square&logo=amazon-aws)](https://www.credly.com/badges/4cdedb8c-35f6-4386-8957-22cc50c51685)
[![Location](https://img.shields.io/badge/Brazil-Remote_UTC--3-green?style=flat-square)](https://linkedin.com/in/danielaugustormelo)

---

## O que eu construí

### [MSP Observability Platform](https://github.com/DanielMelo1/msp-observability-platform)
> Plataforma multi-tenant de monitoramento para MSPs com auto-scaling orientado por SLA

O problema que resolvi: MSPs gerenciam múltiplos clientes com contratos diferentes. Um cliente Fintech com SLA 99.99% não pode ter a mesma política de escalonamento de um SaaS com SLA 99%. Construí um sistema onde cada cliente tem thresholds, réplicas e comportamento de scaling independentes, isolados por namespace no Kubernetes.

- 3 perfis de cliente com SLAs distintos (99% / 99.5% / 99.99%)
- Auto-scaling via webhook: Zabbix trigger → Python handler → kubectl scale
- Redução de 60% no custo do cliente C com off-hours scaling
- Stack: EKS 1.31 · Zabbix 7.0 · Terraform modular · PostgreSQL 15 · IRSA

---

### [DevSecOps Pipeline](https://github.com/DanielMelo1/repo-dev-secops-main)
> SAST + DAST + IaC Security num pipeline só, com credenciais gerenciadas via SSM

A maioria dos pipelines de segurança faz uma coisa — scan de código ou scan de container. Este faz os três: analisa o código (Trivy), testa a aplicação rodando (OWASP ZAP), e verifica a infraestrutura como código. Relatórios com timestamp no S3 para histórico de auditoria.

- Trivy: filesystem + config + vulnerability + secret scan
- OWASP ZAP: DAST automatizado contra aplicação em execução
- SSM Parameter Store: zero credenciais hardcoded no pipeline
- Stack: Terraform · CodePipeline · CodeBuild · Trivy · OWASP ZAP

---

### [Kubernetes Production Platform](https://github.com/DanielMelo1/k8s-production-platform)
> EKS com 11 microsserviços em gRPC, observabilidade completa e deployment automatizado

Deploy de uma aplicação e-commerce com 11 serviços em múltiplas linguagens (Go, Python, Java, Node.js, C#) comunicando via gRPC. O foco foi na plataforma — como provisionar, monitorar, escalar e destruir infraestrutura de forma reproduzível.

- Multi-AZ com HPA e self-healing via liveness/readiness probes
- Prometheus + Grafana para métricas de cluster e pods
- Terraform para toda a infraestrutura (VPC, EKS, IAM, Security Groups)
- Custo estimado documentado por recurso: ~$188/mês

---

### [Serverless Price Monitor](https://github.com/DanielMelo1/MonitorPrecosServerless)
> Monitoramento de preços com Lambda, Step Functions e API Gateway

Arquitetura serverless com 3 Lambdas independentes seguindo Single Responsibility Principle — coleta, processamento e API separados. Step Functions orquestra o fluxo. CI/CD provisionado via Terraform na pasta `ci-cd/`.

- Lambda Python 3.12 · Step Functions · DynamoDB · API Gateway
- AWS SAM para deploy da aplicação + Terraform para CI/CD
- GET /produtos/{id} retorna preço atual e histórico

---

## Stack

```
Cloud        AWS (EKS · EC2 · S3 · RDS · Lambda · CodePipeline · SSM · CloudFront)
Kubernetes   EKS · HPA · IRSA · NetworkPolicy · Helm
IaC          Terraform (modular) · CloudFormation · AWS SAM
CI/CD        GitHub Actions (OIDC) · CodePipeline · CodeBuild · CodeDeploy · Jenkins
Security     Trivy · OWASP ZAP · SonarQube · SSM SecureString · IAM least-privilege
Observability Zabbix · Prometheus · Grafana · CloudWatch
Databases    Aurora MySQL · DocumentDB · DynamoDB · PostgreSQL · Redis
Containers   Docker · containerd · GHCR
Languages    Python · Bash · HCL
```

---

## 13 artigos técnicos no Medium

Documento o que construo — incluindo os erros e como resolvi.  
→ [medium.com/@dreimao4](https://medium.com/@dreimao4)

Temas: DevSecOps · EKS · Aurora · DynamoDB · S3 · CloudFront · CI/CD · Auto Scaling

---

## Contato

- 💼 LinkedIn: [danielaugustormelo](https://linkedin.com/in/danielaugustormelo)
- 📧 Email: dreimao4@gmail.com
- 🌍 Brasil · Remoto · UTC-3
- 🗣️ Português (nativo) · Inglês (avançado) · Espanhol (intermediário)

