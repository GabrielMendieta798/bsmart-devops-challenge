# Bsmart — DevOps Engineer Challenge


## Introducción

Este repositorio contiene la resolución del challenge técnico
para la posición de DevOps Engineer en Bsmart.

La propuesta está orientada a resolver problemas de infraestructura
productiva, mejorar la confiabilidad de los servicios y automatizar
procesos operativos mediante buenas prácticas de DevOps.

## Resumen ejecutivo

| Pregunta | Solución propuesta |
|----------|-------------------|
| 1.1. Diagnóstico | Identificación del filesystem afectado, consumo de almacenamiento, procesos y estado de los servicios. |
| 1.2. Recuperación | Contención del incidente, ampliación segura de EBS y recuperación controlada de los servicios. |
| 1.3. Prevención | CloudWatch Agent, alarmas, SNS, rotación de logs y automatización preventiva mediante SSM. |
| 1.4. Incidentes recurrentes | Análisis de causa raíz, estandarización de infraestructura y mejora continua. |
| 2.1. Docker | Docker Compose, imágenes inmutables en ECR, redes independientes y almacenamiento persistente. |
| 2.2. CI/CD | GitHub Actions, Quality Gates, OIDC, promoción entre ambientes, despliegue mediante SSM y rollback. |
| 2.3. Credenciales | IAM Identity Center, Secrets Manager, mínimo privilegio, rotación y auditoría de accesos. |


## Objetivos

- Diagnosticar incidentes en infraestructura Linux sobre AWS.
- Restablecer servicios productivos preservando la integridad de los datos.
- Implementar estrategias de observabilidad y Self-Healing.
- Prevenir incidentes recurrentes mediante estandarización y automatización.
- Diseñar procesos de despliegue reproducibles y seguros.
- Implementar una gestión centralizada de credenciales.

## Índice

### Parte 1 — Diagnóstico y recuperación

- [Documento completo](docs/01-incident-response.md)
- [1.1. Secuencia de diagnóstico](docs/01-incident-response.md#11-secuencia-de-diagnóstico)
- [1.2. Restablecimiento del servicio](docs/01-incident-response.md#12-restablecimiento-del-servicio)
- [1.3. Estrategia de monitoreo y prevención](docs/01-incident-response.md#13-estrategia-de-monitoreo-y-prevención)
- [1.4. Análisis de incidentes recurrentes](docs/01-incident-response.md#14-análisis-de-incidentes-recurrentes)
- [Referencias técnicas](docs/01-incident-response.md#referencias-técnicas)

### Parte 2 — Diseño y automatización

- [Documento completo](docs/02-deployment-design.md)
- [2.1. Esquema de despliegue con Docker](docs/02-deployment-design.md#21-esquema-de-despliegue-con-docker)
- [2.2. Automatización del proceso desde el push hasta producción](docs/02-deployment-design.md#22-automatización-del-proceso-desde-el-push-hasta-producción)
- [2.3. Gestión segura de credenciales](docs/02-deployment-design.md#23-gestión-segura-de-credenciales)
- [Referencias técnicas](docs/02-deployment-design.md#referencias-técnicas)

### Archivos de configuración

- [Docker Compose](docker-compose.yml)
- [Variables de entorno de ejemplo](.env.example)
- [Workflow de validación automatizada](.github/workflows/validate.yml)

## Validación de la configuración

El repositorio incorpora un workflow de GitHub Actions
que ejecuta automáticamente los siguientes controles:

- Validación de la configuración de Docker Compose.
- Interpolación de variables de entorno.
- Verificación de los tres servicios definidos.
- Verificación de la protección del archivo .env.
- Verificación del versionado de .env.example.

El workflow se ejecuta ante pushes y Pull Requests.

La validación es estática y no requiere credenciales
de AWS ni acceso a infraestructura productiva.

Para reproducir la validación localmente:

```bash
docker compose --env-file .env.example config --quiet
docker compose --env-file .env.example config --services
```

[Consultar ejecuciones de GitHub Actions](https://github.com/GabrielMendieta798/bsmart-devops-challenge/actions)

## Consideraciones técnicas

Las soluciones propuestas consideran la infraestructura descrita
en el challenge y explicitan los supuestos técnicos necesarios.

Se prioriza la continuidad operativa, la seguridad, la simplicidad
y la evolución progresiva de la infraestructura.

Los procedimientos y configuraciones presentados son propuestas
técnicas que deberán validarse antes de su implementación
en ambientes productivos.

## Autor

**Gabriel Mendieta** — DevOps / Cloud Engineer

- [GitHub](https://github.com/GabrielMendieta798)