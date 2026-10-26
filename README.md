# devops-lab

Playbook de Ansible que configura el servidor **devops-lab** con Docker, Docker Compose, Jenkins y Grafana.

## Qué hace el playbook

1. Añade el repositorio oficial de Docker e instala Docker y Docker Compose.
2. Arranca el servicio de Docker y lo habilita al inicio.
3. Añade el usuario al grupo `docker` para usarlo sin `sudo`.
4. Copia al servidor el `compose.yml` y el `Dockerfile` de Jenkins.
5. Levanta con Docker Compose:
   - **Jenkins**, con acceso al Docker del servidor para poder construir imágenes.
   - **Grafana**.
6. Muestra las URLs de acceso y la contraseña inicial de Jenkins.

## Configuración

Todos los datos sensibles (servidor, usuario, contraseñas) se leen de variables de entorno definidas en un fichero `.env`, que no se sube al repositorio. Usa `.env.example` como plantilla:

```bash
cp .env.example .env   # y rellena los valores
```

## Uso

```bash
set -a; source .env; set +a
ansible-playbook playbook.yml
```
