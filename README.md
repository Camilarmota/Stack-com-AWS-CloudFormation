# 📜 AWS CloudFormation - Criando um Stack

## 📌 O que é o CloudFormation?

O **AWS CloudFormation** é um serviço que permite **provisionar e gerenciar recursos da AWS** (como EC2, S3, RDS, IAM, etc.) de forma **automatizada** através de templates em **YAML ou JSON**.

Em vez de criar manualmente cada recurso no console, você define toda a infraestrutura como **código**. Isso traz benefícios como:

* 🔄 Reutilização de templates
* ⚡ Automação e consistência
* 🛠️ Versionamento da infraestrutura
* 🔒 Redução de erros manuais

---

## 🛠️ Criando um Stack no Console da AWS

### 1. Acessar o CloudFormation

* Entre no [Console da AWS](https://console.aws.amazon.com/).
* No menu de serviços, procure por **CloudFormation** e abra o serviço.

---

### 2. Criar um novo Stack

* Clique em **Create stack** → **With new resources (standard)**.
* Escolha como enviar o template:

  * **Upload a template file** (se você tem um arquivo YAML/JSON no seu computador).
  * **Specify an Amazon S3 URL** (se o template está em um bucket).
  * **Use a sample template** (se quiser usar exemplos da AWS).

---

### 3. Configurar os detalhes do Stack

* Insira um **Stack name** (ex: `MeuPrimeiroStack`).
* Preencha os **parâmetros** solicitados pelo template (se houver).

  * Exemplo: nome de bucket, tipo de instância EC2, etc.

---

### 4. Configurar opções avançadas

* Defina permissões, roles do IAM (opcional).
* Configure tags (ex: `Projeto=Exemplo`, `Ambiente=Dev`).
* Escolha políticas de rollback e timeout se necessário.

---

### 5. Revisar e criar

* Revise todas as informações.
* Marque a opção de aceitar a criação de recursos do IAM, caso necessário.
* Clique em **Create stack**.

---

### 6. Acompanhar a criação

* Na aba **Events**, acompanhe o progresso.
* Quando o status ficar como **CREATE\_COMPLETE**, seu stack está pronto. 🎉
* Na aba **Resources**, você verá os recursos provisionados.

---

### 7. Gerenciar o Stack

* **Atualizar (Update)**: para aplicar alterações no template.
* **Excluir (Delete)**: remove todos os recursos criados pelo stack.

---

## 📂 Exemplo de Template (YAML)

Aqui um exemplo simples que cria um **bucket S3**:

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Template simples para criar um bucket S3

Resources:
  MeuBucketS3:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: meu-bucket-exemplo-cloudformation
```

---

## ✅ OBS: 

Com o CloudFormation, você consegue **automatizar sua infraestrutura** e ter controle total sobre o ciclo de vida dos seus recursos. Esse é apenas o primeiro passo — com templates mais avançados, é possível montar arquiteturas completas com **EC2, VPCs, RDS, Lambda, API Gateway** e muito mais.

---


