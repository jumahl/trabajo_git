# Taller de Git para Desarrollo de Software

## Objetivo
El objetivo de este taller fue aprender a utilizar comandos y herramientas intermedias de Git, tales como ramas, merge, rebase, cherry-pick, reflog, y la gestión de conflictos. A través de este proceso, desarrollé una mejor comprensión de la gestión de versiones y la resolución de problemas en el flujo de trabajo colaborativo.

## Pasos Seguidos

### 1. Configuración Inicial
Primero, configuré mi nombre y correo para Git y creé un nuevo repositorio local:
```bash
git config --global user.name "Mi Nombre"
git config --global user.email "miemail@correo.com"
git init nombre-del-proyecto

```

### 2. Creación de la Rama feature y Commits
Creé una nueva rama llamada feature y realicé tres commits con cambios incrementales en el archivo archivo.txt
```bash
git checkout -b feature
echo "Texto inicial" > archivo.txt
git add archivo.txt
git commit -m "Commit inicial"

echo "Texto agregado en feature" >> archivo.txt
git commit -am "Segundo commit en feature"

echo "Otro cambio en feature" >> archivo.txt
git commit -am "Tercer commit en feature"

```
### 3. Merge y Rebase
Realicé un merge tradicional y un rebase de la rama feature en la rama master:
```bash
git checkout master
git merge feature

# Reversión del merge y rebase
git reset --hard HEAD~1
git rebase feature


```
### 4. Uso de Cherry-pick y Reflog
Creé una rama hotfix para realizar una corrección urgente y utilicé cherry-pick para aplicar este cambio en master:
```bash
git checkout -b hotfix
echo "Corrección urgente" >> archivo.txt
git commit -am "Hotfix"
git checkout master
git cherry-pick hotfix


```
### 5. Gestión de Conflictos
Provocamos un conflicto intencionalmente modificando el mismo archivo (conflicto.txt) en las ramas feature y master. Luego resolví el conflicto manualmente:
```bash
git checkout feature
echo "Cambio en feature" > conflicto.txt
git add conflicto.txt
git commit -am "Cambio en feature"

git checkout master
echo "Cambio en master" > conflicto.txt
git add conflicto.txt
git commit -am "Cambio en master"

git merge feature



```