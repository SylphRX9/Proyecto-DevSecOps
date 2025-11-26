# 🚀 Proyecto: Stack Frontend + Backend + Reverse Proxy (Docker Compose)

Este proyecto demuestra cómo crear un stack sencillo compuesto por tres servicios en contenedores Docker:

- **Frontend**: página estática servida por Nginx  
- **Backend**: API sencilla en Flask  
- **Reverse Proxy**: Nginx que enruta `/` al frontend y `/api` al backend  
- Todo orquestado mediante **Docker Compose**

Este proyecto es ideal para practicar Docker en nivel **básico + intermedio**.

---

## 📦 Estructura del Proyecto

```
/stack
  ├── frontend/
  │     ├── index.html
  │     └── style.css
  ├── backend/
  │     ├── .dockerignore
  │     ├── Servidor.py
  │     ├── requisitos.txt
  │     └── Dockerfile
  ├── nginx/
  │     └── nginx.conf
  └── docker-compose.yml
```

---

## ⚙️ Tecnologías utilizadas

- Docker  
- Docker Compose  
- Nginx  
- Python + Flask  
- Redes Docker tipo bridge  

---

## 🧩 Cómo funciona el stack

### 🔹 Frontend
El frontend es una página estática servida por Nginx.  
Es accesible desde:

```
http://localhost/
```

### 🔹 Backend (Flask)
API muy simple que responde un JSON.  
Es accesible desde:

```
http://localhost/api
```

El reverse proxy se encarga de redirigir esta ruta.

### 🔹 Reverse Proxy (Nginx)
El archivo `nginx.conf` define el ruteo:

- `/` → servicio `frontend`
- `/api` → servicio `backend`

Gracias a Docker Compose, todos los servicios se comunican por nombre interno.

---

## ▶️ Cómo ejecutar el proyecto

1. Clonar el repositorio:
```bash
git clone https://github.com/SylphRX9/Proyecto-DevSecOps.git
cd Proyecto-DevSecOps
```

2. Construir y levantar el stack:
```bash
docker-compose up --build
```

3. Abrir en el navegador:
- http://localhost → frontend  
- http://localhost/api → backend  

---

## 🛑 Detener el stack

```bash
docker-compose down
```

---

## 🐳 Comandos útiles

```bash
docker ps                # Ver contenedores
docker-compose logs -f   # Ver logs en tiempo real
docker-compose build     # Reconstruir imágenes
```

---

## 🧠 Aprendizajes obtenidos

- Crear y usar múltiples Dockerfiles  
- Construir imágenes personalizadas  
- Usar Docker Compose para orquestar varios contenedores  
- Crear redes internas y comunicar servicios  
- Configurar un reverse proxy real con Nginx  
- Separar frontend, backend y proxy correctamente  

---

## ⭐ Mejoras recomendadas

- Habilitar HTTPS con Certbot  
- Agregar CI/CD con GitHub Actions  
- Desplegar en un VPS o Azure Container Apps  

---

## 📄 Licencia

Este proyecto puede usarse libremente con fines educativos y prácticos.
