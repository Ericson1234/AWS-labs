# ☁️ AWS Labs

Colección de laboratorios prácticos en **AWS** enfocados en cómputo, almacenamiento, redes, infraestructura como código (IaC) y serverless. Cada carpeta representa un ejercicio hands-on con los comandos, plantillas y código usados para desplegarlo.

![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat&logo=amazonaws&logoColor=white)
![CloudFormation](https://img.shields.io/badge/CloudFormation-527FFF?style=flat&logo=amazonaws&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-blue)

## 🎯 Objetivo del repositorio

Este repositorio documenta mi proceso de aprendizaje práctico en AWS, cubriendo servicios core que se usan en arquitecturas reales en la nube: desde levantar una instancia EC2 y alojar un sitio estático en S3, hasta desplegar infraestructura completa con CloudFormation y exponer una API serverless con Lambda + API Gateway.

## 🗂️ Laboratorios incluidos

| Lab | Servicios AWS | Qué demuestra |
|---|---|---|
| [`aws-api-gateway-lambda/`](./aws-api-gateway-lambda) | API Gateway, Lambda | Integración Lambda proxy: función Node.js que procesa query params, headers y body de una petición REST |
| [`aws-cloudformation/`](./aws-cloudformation) | CloudFormation, S3, VPC | Infraestructura como código: bucket S3 (con y sin cifrado SSE) y una VPC completa multi-AZ (subnets públicas/privadas, Internet Gateway, tablas de ruteo) |
| [`aws-ec2/`](./aws-ec2) | EC2 | Ciclo de vida de instancias vía CLI (lanzar, describir, terminar), script `user-data` para servir contenido dinámico desde S3, prueba de estrés de CPU |
| [`aws-ebs/`](./aws-ebs) | EC2 / AMI | Creación de una AMI personalizada con `user-data` para bootstrapping automático de un servidor web |
| [`aws-elastic-beanstalk-nodejs/`](./aws-elastic-beanstalk-nodejs) | Elastic Beanstalk, Node.js | App Node.js desplegada en Elastic Beanstalk, incluyendo tareas programadas (`cron.yaml`) |
| [`aws-lambda/`](./aws-lambda) | Lambda, SQS, SNS | Invocación de funciones vía CLI (payload base64), función disparada por eventos de SQS, política de acceso SNS → SQS |
| [`aws-s3/`](./aws-s3) | S3 | Comandos CLI para gestión de buckets, política de acceso público, hosting de sitio web estático |
| [`aws-vpc.md`](./aws-vpc.md) | VPC | Diseño manual de una VPC con subnets públicas/privadas, Internet Gateway y NAT Gateway |
| [`misc/`](./misc) | CloudFront, EFS, Git, CLI Windows | Política de Origin Access Control para CloudFront + S3, montaje de EFS, comandos básicos de Git y de consola Windows |

## 🛠️ Skills demostradas

- **Cómputo**: EC2 (ciclo de vida, AMIs, user-data), Elastic Beanstalk, Lambda (serverless)
- **Almacenamiento**: S3 (hosting estático, políticas de bucket), EBS, EFS
- **Redes**: diseño de VPC multi-AZ, subnets públicas/privadas, Internet/NAT Gateway, CloudFront + Origin Access Control
- **IaC**: CloudFormation (plantillas YAML reutilizables con parámetros y outputs)
- **APIs**: API Gateway con integración Lambda proxy
- **Mensajería/eventos**: integración SNS → SQS → Lambda
- **Seguridad**: políticas IAM/bucket con principio de mínimo privilegio

## 🚀 Cómo reproducir un lab

Cada carpeta incluye los comandos AWS CLI o la plantilla necesaria. Requisitos generales:

```bash
# AWS CLI configurado con credenciales propias
aws configure

# Ejemplo: desplegar la VPC con CloudFormation
aws cloudformation create-stack \
  --stack-name mi-vpc \
  --template-body file://aws-cloudformation/vpc.yml \
  --parameters ParameterKey=EnvironmentName,ParameterValue=Produccion
```

> ⚠️ Reemplaza cualquier ARN, Account ID o nombre de bucket de ejemplo por los tuyos antes de ejecutar.

## 📌 Notas

Este repositorio está en evolución constante conforme sigo profundizando en arquitecturas AWS (actualmente explorando patrones de alta disponibilidad y buenas prácticas de seguridad para el examen de certificación).

## 📄 Licencia

MIT
