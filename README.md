# 🚀 Plantilla Dev Container para .NET 8

Esta plantilla permite configurar en minutos un entorno de desarrollo listo para proyectos **.NET 8**, usando **Visual Studio Code** y **Dev Containers**.  
Olvidate de los problemas de compatibilidad y del "funciona en mi máquina".

---

## 📦 Características

- **SDK .NET 8** preinstalado.
- Extensiones de VS Code configuradas automáticamente:
  - [C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)
  - [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
  - [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- Puertos preconfigurados:
  - `5000` (ejemplo: ASP.NET Core)
  - `1433` (ejemplo: SQL Server)
- `postCreateCommand` para restaurar y compilar el proyecto automáticamente.

---

## 📂 Estructura del proyecto

```
.devcontainer/
│── devcontainer.json
│── Dockerfile (opcional)
src/
│── (aquí tu código .NET)
```

---

## 🚀 Cómo usarlo

### 1. Requisitos previos
- [Visual Studio Code](https://code.visualstudio.com/)
- [Extensión Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
- [Docker Desktop](https://www.docker.com/products/docker-desktop) (o Docker compatible)

---

### 2. Pasos para iniciar
1. Clonar el repositorio:
   ```bash
   git clone https://github.com/tuusuario/dotnet8-devcontainer.git
   ```
2. Abrir la carpeta en **VS Code**.
3. Cuando aparezca la notificación, seleccionar **"Reopen in Container"**.
4. Esperar a que se construya el entorno (solo la primera vez).
5. ¡Listo! Tu proyecto .NET 8 está listo para usarse.

---

## 🛠 Ejemplo de `devcontainer.json`

```json
{
  "name": "Dotnet 8 Dev Container",
  "image": "mcr.microsoft.com/devcontainers/dotnet:8.0",
  "customizations": {
    "vscode": {
      "extensions": [
        "ms-dotnettools.csharp",
        "ms-azuretools.vscode-docker",
        "eamodio.gitlens"
      ]
    }
  },
  "forwardPorts": [5000, 1433],
  "postCreateCommand": "dotnet restore && dotnet build",
  "remoteUser": "vscode"
}
```

---

## 💡 Notas
- Si querés agregar más herramientas, podés editar el archivo `devcontainer.json`.
- Si tu proyecto necesita base de datos, podés añadir contenedores adicionales usando `docker-compose.yml`.

---

## 📜 Licencia
Este proyecto está bajo licencia MIT. Podés usarlo, modificarlo y compartirlo libremente.
