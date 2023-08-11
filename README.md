# Demo de AWS Community Day (Implementando  MLFLow en tus experimentos de ML a bajo costo desde EC2)

## Introduccion

Este repositorio tiene la informacion necesaria para seguir el demo de la presentacion de **Usando MLflow con EC2 a bajo costo** en el ambiente del [AWS Community Day Colombia](https://awscommunitydaycolombia.splashthat.com/)

Este repositorio tendra diferentes partes para la instalaciòn y configuraciòn de servicios de AWS de acuerdo a la siguiente arquitectura:

![Arquitectura](./docs/readme/arquitect_temp2.png)

## Enlace relevante

[Guia del Demo con el paso a paso para implementacion](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)

## Audiencia
- Equipos de ciencia de datos que quieren dar sus primeros pasos en AWS y mejorar procesos de ML
- Individuos con rol de Cientifico de datos (Data Scientist)
- Individuos con rol de Ingenieros de datos (Data Engineer)
- Individuos con rol de Ingenieros ML (ML Engineer)
- Cualquier otro rol que requiera experiencia práctica para realizar *tracking* de parametros y artefactos relacionados con la administracion de modelos de aprendizaje automático

## Metas
- Introduccion a servicios de AWS que pueden integrarse con MLflow
- Introduccion a MLFLow
- Entendimiento de caracteristicas relevantes de MLflow que se veran reflejadas en el servidor de MLflow desplegado dado arquitectura. 

## Resumen

En este Workdshop/Demo, se discutira: *Usando MLflow con EC2 a bajo costo*.

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
- [Parte 2.1: Creaciòn y configuraciòn de instancia de EC2 para MLFlow](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 2.2: Configuraciòn de IP elastica para la instancia de EC2 en red publica. Luego, se puede generar AMI para pasar a red privada](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 3: Configuraciòn del balanceador de carga para establecer dominio del servidor MLflow](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Parte 4: Introducciòn a MLFlow y uso desde Jupyter Notebooks](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)
- [Tips](https://docs.google.com/document/d/1Z1-JeTC9gg58TH4lwZOdo67CkA6W0z8fDMJapOrs8Tg/edit?usp=sharing)

## Estructura del repositorio
> Nota: Esta es la estructura del repositorio desde la raiz
- `README.md` > README de
- `aws_configuration` > Carpeta donde se encuentran las politicas de permisos de ec2 en formato json
- `notebooks_demo` > Jupyter Notebooks en donde se encuentran los casos de uso del servidor de MLflow deslegado en AWS
- `data` > Se encuentran archivos para usar en los casos de uso dentro de notebooks_demo
- `docs` > Se encuentra informacion auxiliar del repositorio

## Workshop Scenario (FALTA)
> **Note: Read before starting the workshop!**

Your team has been working on a new machine learning (ML) problem (predicting taxi fares in New York). The
team has been performing exploratory work on the data and has come to a state where the model is solidified.
Now, it is time to put a structure into the work so that the team can iterate faster toward building a fully
functional solution. So far, team members have been working mostly with Jupyter notebooks on their
personal compute.

To re-engineer this into a functional MLOps process, the following steps will be taken:
1. The code will be modularized (refactored into separate python modules) and parameterized (configured so it
   can be re-run with different values). This will lay the foundation for good software practices and allow
   multiple data scientists/engineers to work collaboratively on the code. (Later, we will reinforce DevOps
   practices around continuous integration and continuous deployment with specific workflows to support model
   training and evaluation. MLOps builds off a strong foundation in DevOps and looks to additionally manage
   the model and data lifecycles to support the best model in production.)
2. After successfully restructuring the Jupyter notebook and running the modules locally, your team will
   leverage Microsoft Azure to run the ML experiment at scale. They will take advantage of experiment tracking
   and model management capabilities in Azure ML to keep track of experiments. The team will then deploy the
   model as a rest endpoint for real time inferencing.
4. They will then setup a centralized version control in Github to keep track of project code and manage different
   feature development tracks and releases. They will need to understand how to automate and orchestrate
   common tasks such as environment setup, training, and testing.
5. After setting up GitHub for MLOps, your team will start automating the model training and evaluation
   process with a Continuous Integration (CI) pipeline.
6. After a successful run of the CI pipeline, your team will complete the process with a Continuous
   Delivery (CD) pipeline that will handle the deployment of the model without introducing any downtime in
   production (hot swap).
7. Now, head to [Workshop Environment Setup: Part 0](https://github.com/microsoft/MLOpsTemplate/blob/main/src/workshop/documents/part_0.md#part-0-workshop-environment-setup)

## Video (FALTA)

Embed your Train the Trainer video here. Instructions on how to create a great video experience is [available on this page](../video-guidance.md).

- [Introduccion](link)
- [Parte 1: Adecuaciòn de  VPC](link)
- [Parte 2.0: Configuraciòn rol, instancia EC2 y bucket  en S3](link)
- [Parte 2.1: Creaciòn y configuraciòn de instancia de EC2 para MLFlow](link)
- [Parte 2.2: Configuraciòn de IP elastica para la instancia de EC2 en red publica. Luego, se puede generar AMI para pasar a red privada](link)
- [Parte 3: Configuraciòn del balanceador de carga para establecer dominio del servidor MLflow](link)
- [Parte 4: Introducciòn a MLFlow y uso desde Jupyter Notebooks](link)
- [Tips](link)

## Pre-Learning

- [Introduccion a Git (En Ingles)](https://www.youtube.com/watch?v=uR6G2v_WsRA&ab_channel=DavidMahler)

## Contributing (FALTA)
This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.


