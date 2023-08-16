# AWS Community Day Demo (Implementing MLflow in your ML experiments at low cost from EC2)

- 💼 [LinkedIn](https://www.linkedin.com/in/kamymartinez/)
- 🐦 [Twitter](https://twitter.com/kamynz16)

- Demo in [Spanish](https://github.com/KamyNz/awscomunityday2023/tree/demo_spanish)

## Introduction

This repository contains the necessary information to follow the demo from the presentation **Using MLflow with Low-Cost EC2** in the context of the [AWS Community Day Colombia](https://awscommunitydaycolombia.splashthat.com/) event.

The repository is structured into various sections for the installation and configuration of AWS services, following the architecture outlined below:

![Arquitectura](./docs/readme/Arquitecturav2.png)

## Key Links (Falta)

[Demo Guide in English]()

## Key Audience
- Data science teams looking to take their first steps on AWS and enhance ML processes
- Individuals with a Data Scientist role
- Individuals with a Data Engineer role
- Individuals with an ML Engineer role
- Any other role seeking practical experience for tracking parameters and artifacts related to managing machine learning models.

## Goals
- Introduction to the AWS architecture used to generate the MLflow Tracking server
- Introduction to MLflow
- Interaction with MLflow from an instance in a private network that uses a balancer

## Demo Scenario
> **Note: Read the following before you begin!**

An analytics team wants to start implementing an MLOps culture. Therefore, along with their technical leader, they are going to set up a tracking server using [MLflow](https://mlflow.org/docs/latest/what-is-mlflow.html) on [AWS](https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/well-architected-machine-learning.html) infrastructure, as per their organization's directives to use this cloud platform.

Similarly, the technical leader of the analytics team aims to streamline the compilation of the library of experiments that team members have been generating in Jupyter notebooks on their personal computers.

## Summary
En este Workdshop/Demo, se discutira: *Usando MLflow a bajo costo en una instancia EC2*.

| **Metas**              | *Ver seccion de Metas arriba*                                    |
| ----------------------------- | --------------------------------------------------------------------- |
| **Que aprenderas**       | *Uso de servicios de AWS: EC2, S3 para implementar el software de Open Source de MLFlow*                                   |
| **Que necesitaras**          | *Cuenta de AWS con free tier* |
| **Duration**                  | *1h*                                                                |
| **Temas**                  | *EC2, uso de systemctl en EC2, S3, MLFLow*                                                                |                       |
| **Slides** | [Powerpoint](slides.pptx)

## Prerequisitos relevantes

- Se debe tener cuenta de AWS
- Se recomienda que a partir de la cuenta root, se debe generar un rol que usaremos para disponibilizar los servicios de AWS de la demo como:
   - VPCs
   - Grupo de seguridad (Security Group)
   - Instancia de EC2
   - Buckets de S3
   - Grupo destinatario (Target group)
   - Balanceador de Carga (Load balancer)

> Nota: En lenguaje de la consola sobre la cual se hicieron las partes del demo esta en Ingles por 2 razones: i) en el futuro sera màs facil generalizar el material para otros usos y ii) se practica ingles.  

## Estructura de la Guia del Demo 
- [Lista de Chequeo de Pre-Workshop](docs/extra_md/part_tips.md)
- [Introduccion](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 1: Adecuaciòn de  VPC](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 2.0: Configuraciòn rol, instancia EC2 y bucket  en S3](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 2.1: Configuración de instancia de EC2 para MLflow](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 2.2: Configuraciòn de IP elastica para la instancia de EC2 en red publica. Luego, se puede generar AMI para pasar a red privada](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 3: Configuraciòn del balanceador de carga para establecer dominio del servidor MLflow](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 4: Introducciòn a MLFlow y uso desde Jupyter Notebooks](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Tips](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)

## Estructura del repositorio
> Nota: Esta es la estructura del repositorio desde la raiz
- `README.md` > README con las indicacioens de uso de este repositorio
- `aws_configuration` > Carpeta donde se encuentran las politicas de permisos de ec2 en formato json
- `notebooks_demo` > Jupyter Notebooks en donde se encuentran los casos de uso del servidor de MLflow deslegado en AWS
- `data` > Se encuentran archivos para usar en los casos de uso dentro de notebooks_demo
- `docs` > Se encuentra informacion auxiliar del repositorio

## Video

- [Introduccion](https://www.youtube.com/playlist?list=PL3wXgEANpNm0fDGriRgHSTrAfY3SV_6sH)
- Parte 1: Adecuaciòn de  VPC
- [Parte 2.0: Configuraciòn rol, instancia EC2 y bucket  en S3](https://www.youtube.com/playlist?list=PL3wXgEANpNm0fDGriRgHSTrAfY3SV_6sH)
- [Parte 2.1: Configuración de instancia de EC2 para MLflow](https://www.youtube.com/playlist?list=PL3wXgEANpNm0fDGriRgHSTrAfY3SV_6sH)
- Parte 2.2: Configuraciòn de IP elastica para la instancia de EC2 en red publica. Luego, se puede generar AMI para pasar a red privada
- Parte 3: Configuraciòn del balanceador de carga para establecer dominio del servidor MLflow
- [Parte 4: Introducciòn a MLFlow y uso desde Jupyter Notebooks](https://youtu.be/uuQsK4kUoKQ)
- [Tips](https://www.youtube.com/playlist?list=PL3wXgEANpNm0fDGriRgHSTrAfY3SV_6sH)

## Pre-Learning

- [Introduccion a Git (En Ingles)](https://www.youtube.com/watch?v=uR6G2v_WsRA&ab_channel=DavidMahler)

## Learnings, and next steps.

- Desarrollar el demo con Terraform para facilitar uso de servicio dado Infraestructura como Codigo (IaC)

## Agradecimientos 

- [Jeico Percy](https://www.linkedin.com/in/jeico-percy-ing-redes/): Ofrecerme apoyo y su conocimiento en validar las buenas practicas en AWS para este ejercicio.
- [Ana Maria Lopez](https://www.linkedin.com/in/amlopez81/): Darme realimentacion del material de esta charla
- [Diego Marulanda](https://www.linkedin.com/in/diegomarulandabarrientos/): Escuchar mi presentacion y darme realimentacion
- [Juanita Herrera](https://www.linkedin.com/in/juanita-herrera-9152b2172/): Escuchar mi presentacion y hacer que tenga los mejores resultados


