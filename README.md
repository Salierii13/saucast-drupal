# 🐳 Proyecto Drupal con DDEV - Saucast

Este proyecto configura un entorno de desarrollo local para Drupal 11 usando DDEV, con:

- ⚙️ Drupal 11 con un tema custom llamado `saucast`
- 🐋 Gestión de entorno con DDEV y Docker
- 🎨 Compilación de SCSS para el tema `saucast`
- 💾 Base de datos inicial opcional para importar

---

## ✅ Requisitos previos

- Docker Desktop (asegúrate que Docker esté corriendo)
- DDEV instalado y configurado
- Node.js y npm (para compilar SCSS)
- PowerShell o CMD en Windows (preferido PowerShell)

---

## 📁 Estructura esperada del proyecto
```
project-root/
├── .ddev/ # Configuración DDEV
├── db/ # Base de datos inicial (optional)
│ └── initial.sql
├── web/
│ ├── themes/
│ │ └── custom/saucast
│ │ └── saucast/ # Tema custom con SCSS
│ │ ├── scss/
│ │ ├── css/
│ │ ├── saucast.info.yml
│ │ └── package.json
├── .gitignore
└── README.md
```
---

## 🧪 Comandos para trabajar con DDEV y Drupal

### 🚀 Levantar el entorno

```bash
ddev start
```
Esto iniciará los contenedores Docker y te mostrará la URL local para acceder al sitio Drupal.

### 🔽 Detener los contenedores (down)
```bash
ddev stop
```

###🗄️ Importar base de datos inicial (opcional)
```bash
ddev import-db --src=db/initial.sql
```
📤 Exportar base de datos (backup)
Para exportar la base de datos en formato plano sin compresión:

```bash
ddev export-db --gzip=false --file=db/export.sql
```

### 🐘 Acceder al contenedor PHP (shell)
```bash
ddev ssh
```

## 🎨 Compilar SCSS del tema saucast
Entra a la carpeta del tema (desde dentro del contenedor php):

````bash
cd web/themes/custom/saucast
````

Instala dependencias (solo la primera vez):

````bash
npm install
````

Compila el SCSS:

Una sola vez:
````bash
npm run build
````

Mantener escuchando:
````bash
npm run watch
````



Esto generará el CSS compilado en web/themes/custom/saucast/css/style.css.

# 🌐 Acceder al proyecto en el navegador
https://entorno.ddev.site


