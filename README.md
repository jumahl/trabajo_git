# Taller de Git 


### 1. Creación de la Rama feature y Commits
Creé una nueva rama llamada feature y realicé tres commits con cambios incrementales en el archivo archivo.txt
```bash
git init trabajo_git
git checkout -b feature
echo "Texto inicial" > archivo.txt
git add archivo.txt
git commit -m "Commit inicial"

echo "Texto agregado en feature" >> archivo.txt
git commit -am "Segundo commit en feature"

echo "Otro cambio en feature" >> archivo.txt
git commit -am "Tercer commit en feature"

```
### 2. Merge y Rebase
Realicé un merge tradicional y un rebase de la rama feature en la rama master:
```bash
git checkout master
git merge feature

# Reversión del merge y rebase
git reset --hard HEAD~1
git rebase feature


```
### 3. Uso de Cherry-pick y Reflog
Creé una rama hotfix para realizar una corrección urgente y utilicé cherry-pick para aplicar este cambio en master:
```bash
git checkout -b hotfix
echo "Corrección urgente" >> archivo.txt
git commit -am "Hotfix"
git checkout master
git cherry-pick hotfix


```
### 4. Gestión de Conflictos
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
