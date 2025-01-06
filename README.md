# Atividade Final - Arquitetura Cloud, Git e IaC

Este repositório contém a documentação e exemplos práticos relacionados à migração de infraestrutura para a nuvem, práticas de Git, pipelines de CI/CD e uso de Infrastructure as Code (IaC) com Terraform. Abaixo, estão descritos os principais tópicos abordados.

## 1. Migração para Nuvem

### 1.1 Migração de VMs para Provedor de Nuvem Pública (AWS)
- **Passos da migração:**
  1. Planejamento e inventário das VMs.
  2. Criação do ambiente na nuvem (VPC, instâncias EC2, grupos de segurança).
  3. Ferramentas como AWS Migration Hub ou AWS Server Migration Service.
  4. Testes e validação após a migração.
  5. Desativação da infraestrutura on-premises.

### 1.2 Migração de VMs para Containers
- **Orquestradores:** Kubernetes (EKS) ou Amazon ECS.
- **Passos principais:**
  1. Planejamento e identificação das aplicações a serem containerizadas.
  2. Criação de `Dockerfile`.
  3. Build e push das imagens para repositórios como Amazon ECR.
  4. Configuração e deploy com Kubernetes.

### 1.3 Escalabilidade com Kubernetes e Nomad
- **Kubernetes:**
  - Horizontal Pod Autoscaler (HPA) e Vertical Pod Autoscaler (VPA).
  - Uso de ferramentas de monitoramento como Prometheus e Grafana.
- **Nomad:**
  - Simplicidade para escalabilidade em ambientes menores.
  - Integração com Consul e Vault.

## 2. Práticas com Git

### 2.1 Criação de Commits
- Granularidade e mensagens claras.
- Uso de comandos como `git add`, `git commit`, e `git push`.

### 2.2 Fluxo de Pull Requests
- Criação de branches para features (`git checkout -b`).
- Envio de modificações (`git push origin <branch>`).
- Revisão e merge das alterações via Pull Request.

## 3. Pipeline CI/CD

### 3.1 Configuração com GitHub Actions
- Etapas do pipeline:
  1. Checkout do código.
  2. Build de imagens Docker.
  3. Push para Amazon ECR.
  4. Deploy para ECS ou EKS.

### 3.2 Atualizações Automáticas
- Detecção de eventos no repositório.
- Automação do rebuild e redeploy.

### 3.3 Boas Práticas de Segurança
- Uso de GitHub Secrets para armazenar credenciais.
- Princípio do menor privilégio para permissões IAM.
- Scans de vulnerabilidade com ferramentas como Trivy.

## 4. Infraestrutura de Codigo com Terraform

### 4.1 Manifestos para Provisionamento de Recursos
- Exemplos incluem:
  - Configuração de VPC, subnets e instâncias EC2.
  - Criação de repositórios ECR.

### 4.2 Organização dos Arquivos
- Divisão lógica em `main.tf`, `network.tf`, `compute.tf`, etc.
- Uso de variáveis e outputs.

### 4.3 Boas Práticas
- Evitar hardcoding de dados sensíveis.
- Uso de estados remotos com Amazon S3 e DynamoDB.
- Modularização para reaproveitamento de código.

## 5. Conclusão

Esta documentação serve como referência para implementar uma arquitetura robusta na nuvem, utilizando boas práticas de DevOps e IaC. Siga as instruções fornecidas para adaptar as soluções às necessidades específicas do seu ambiente.
