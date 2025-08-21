# Mock Backend con JSON

Este proyecto proporciona un **servidor de prueba (mock backend)** basado en un archivo JSON. Fue útil para simular una API REST mientras se desarrolla el frontend para la prueba de [Trustcore](https://trustcore-services.com/), sin necesidad de tener un backend real implementado.

## 🚀 Requisitos

- [Node.js](https://nodejs.org/) (versión 14 o superior)
- [npm](https://www.npmjs.com/) o [yarn](https://yarnpkg.com/)

## 📦 Instalación

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/mock-backend.git
   cd mock-backend
   ```

2. Instala las dependencias:
   ```bash
   npm install
   ```
   o
   ```bash
   yarn install
   ```

## ▶️ Ejecución

Ejecuta el servidor mock con:
```bash
npm run start
```

Por defecto se levantará en:
👉 **http://localhost:4001**

## 📂 Estructura del proyecto

```
backFileUpload/
├── src/data/db.json # Archivo principal que simula la base de datos
├── package.json     # Dependencias y scripts
└── README.md        # Este archivo
```

### Archivo `db.json`

Contiene los datos de ejemplo en formato JSON. Cada propiedad dentro de este archivo representa un "endpoint".

```json
{
  "files": [
    [
      {
        "name": "Respuestas a Dudas y cambios Esteban 19 de agosto 2025.docx",
        "type": "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
        "size": "2.83 MB",
        "createdAt": "21/8/2025",
        "createdBy": "UserFile",
        "tag": "Trabajo"
      },
      {
        "name": "CATALOGO-SER-CROCHET-2025.pdf",
        "type": "application/pdf",
        "size": "3.24 MB",
        "createdAt": "21/8/2025",
        "createdBy": "UserFile",
        "tag": "Trabajo"
      },
      {
        "name": "Group 39156.jpg",
        "type": "image/jpeg",
        "size": "0.23 MB",
        "createdAt": "21/8/2025",
        "createdBy": "UserFile",
        "tag": "Trabajo"
      }
    ]
  ]
}
```

## 🛠️ Tecnologías utilizadas

- **json-server** → Herramienta que convierte un archivo JSON en una API REST completa

## 📝 Ejemplos de uso

### Obtener todos los usuarios
```bash
curl http://localhost:4001/files
```

### Crear un nuevo archivo
```bash
curl -X POST \
  http://localhost:3000/files\
  -H 'Content-Type: application/json' \
  -d '{
        "name": "Group 39156.jpg",
        "type": "image/jpeg",
        "size": "0.23 MB",
        "createdAt": "21/8/2025",
        "createdBy": "UserFile",
        "tag": "Trabajo"
      }'
```


## 🔧 Configuración adicional

Puedes personalizar el comportamiento del servidor modificando el `package.json`:

```json
{
  "scripts": {
    "start": "json-server --watch db.json --port 3000 --delay 500"
  }
}
```

### Parámetros útiles:
- `--port` → Cambiar puerto (por defecto 3000)
- `--delay` → Agregar retraso a las respuestas (útil para simular latencia)
- `--watch` → Recarga automática al modificar db.json

---

**¡Listo para usar!** 🎉 Este mock backend te permitirá desarrollar tu frontend de manera independiente y eficiente.
