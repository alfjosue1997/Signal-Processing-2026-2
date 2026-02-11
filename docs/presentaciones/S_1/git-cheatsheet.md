# Git Cheat Sheet - Comandos Esenciales

## 🔧 Configuración Inicial

```bash
# Configurar nombre de usuario
git config --global user.name "Tu Nombre"

# Configurar email
git config --global user.email "tu@email.com"

# Ver configuración actual
git config --list
```

## 📦 Crear y Clonar Repositorios

```bash
# Inicializar un nuevo repositorio local
git init

# Clonar un repositorio existente
git clone <url-del-repositorio>

# Clonar con un nombre específico
git clone <url> <nombre-carpeta>
```

## 📝 Trabajar con Cambios

```bash
# Ver estado de archivos
git status

# Agregar archivo específico al staging area
git add <nombre-archivo>

# Agregar todos los archivos modificados
git add .

# Crear un commit con mensaje
git commit -m "Mensaje descriptivo del commit"

# Ver historial de commits
git log

# Ver historial resumido (una línea por commit)
git log --oneline

# Ver historial con gráfico de branches
git log --oneline --graph --all
```

## 🌿 Trabajar con Branches (Ramas)

```bash
# Ver todas las ramas
git branch

# Crear una nueva rama
git branch <nombre-rama>

# Cambiar a otra rama
git checkout <nombre-rama>

# Crear y cambiar a nueva rama en un solo comando
git checkout -b <nombre-rama>

# Fusionar una rama con la actual
git merge <nombre-rama>

# Eliminar una rama local
git branch -d <nombre-rama>

# Eliminar una rama remota
git push origin --delete <nombre-rama>
```

## 🔄 Sincronización con Repositorio Remoto

```bash
# Ver repositorios remotos configurados
git remote -v

# Agregar un repositorio remoto
git remote add <nombre> <url>

# Agregar repositorio origin
git remote add origin <url>

# Agregar repositorio upstream (para forks)
git remote add upstream <url>

# Descargar cambios del remoto (sin fusionar)
git fetch origin

# Descargar y fusionar cambios del remoto
git pull origin <rama>

# Subir commits al repositorio remoto
git push origin <rama>

# Subir todos los branches
git push --all origin

# Subir la rama actual por primera vez
git push -u origin <rama>
```

## ⏮️ Deshacer Cambios

```bash
# Quitar archivo del staging area (después de add)
git reset HEAD <archivo>

# Deshacer último commit (mantener cambios)
git reset --soft HEAD~1

# Deshacer último commit (descartar cambios)
git reset --hard HEAD~1
```

## 📋 .gitignore

```bash
# Archivo de configuración para ignorar archivos
# Crear archivo .gitignore en la raíz del proyecto

# Ejemplos de contenido:
# *.pyc              # Ignorar todos los .pyc
# __pycache__/       # Ignorar carpeta __pycache__
# *.log              # Ignorar archivos de log
# datos/*.csv        # Ignorar CSVs en carpeta datos
# !importante.csv    # Excepto este archivo
# .DS_Store          # Archivos de macOS
# .vscode/           # Configuración de VS Code
```

## 🍴 Trabajo con Forks

```bash
# 1. Hacer fork en GitHub (botón Fork)

# 2. Clonar tu fork
git clone <url-de-tu-fork>

# 3. Agregar repositorio original como upstream
git remote add upstream <url-repositorio-original>

# 4. Verificar remotos
git remote -v

# 5. Mantener tu fork actualizado
git fetch upstream
git checkout main
git merge upstream/main
git push origin main

# 6. Trabajar en una nueva rama para tu contribución
git checkout -b mi-contribucion

# 7. Hacer cambios, commit y push a tu fork
git add .
git commit -m "Descripción de cambios"
git push origin mi-contribucion

# 8. Crear Pull Request en GitHub
```

## 💡 Buenas Prácticas

### Mensajes de Commit

```bash
# Formato recomendado:
# <tipo>: <descripción breve>
#
# Tipos comunes:
# Add:      Agregar nueva funcionalidad
# Fix:      Corregir un bug
# Update:   Actualizar código existente
# Remove:   Eliminar código o archivos
# Refactor: Mejorar código sin cambiar funcionalidad
# Docs:     Cambios en documentación

# Ejemplos:
git commit -m "Add: Función para calcular FFT"
git commit -m "Fix: Error en filtro Butterworth"
git commit -m "Update: Optimizar algoritmo de convolución"
git commit -m "Docs: Agregar comentarios a clase Signal"
```

### Flujo de Trabajo Colaborativo

```bash
# 1. Actualizar main antes de empezar
git checkout main
git pull origin main

# 2. Crear rama para nueva feature
git checkout -b feature/nombre-descriptivo

# 3. Trabajar y hacer commits
git add .
git commit -m "Add: nueva funcionalidad"

# 4. Actualizar con cambios del main
git checkout main
git pull origin main
git checkout feature/nombre-descriptivo
git merge main

# 5. Resolver conflictos si existen

# 6. Push de la rama
git push origin feature/nombre-descriptivo

# 7. Crear Pull Request en GitHub

# 8. Después de merge, limpiar
git checkout main
git pull origin main
git branch -d feature/nombre-descriptivo
```

## 🆘 Comandos de Ayuda

```bash
# Ayuda general
git help

# Ayuda de comando específico
git help <comando>
git <comando> --help

# Ejemplos:
git help commit
git help branch
```

## 🎯 Comandos para Esta Clase

```bash
# Secuencia básica de trabajo:
git clone <url>                    # Clonar repositorio
cd <nombre-repo>                   # Entrar al directorio
git checkout -b develop            # Crear rama develop
# ... hacer cambios ...
git add .                          # Agregar cambios
git commit -m "Mensaje"            # Hacer commit
git push origin develop            # Subir rama
git checkout main                  # Cambiar a main
git merge develop                  # Fusionar develop en main
git push origin main               # Subir main actualizado
```

---

**Nota:** Este cheat sheet cubre los comandos esenciales para la clase. Para información más detallada, consulta la [documentación oficial de Git](https://git-scm.com/doc).
