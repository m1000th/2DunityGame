# Cómo subir el proyecto a GitHub e invitar al equipo

## 1. Crear el repositorio en GitHub

1. Entrar a https://github.com/new
2. Elegir un nombre para el repo (ej. `nuestro-juego`).
3. Marcarlo como **Private** (recomendado mientras el juego esté en desarrollo).
4. **No** tildar "Add a README" ni ".gitignore" ni "license" — ya los tenemos preparados en esta carpeta.
5. Crear el repositorio.

## 2. Invitar a tus 3 compañeros

Dentro del repo recién creado:

1. Ir a **Settings > Collaborators** (puede pedir confirmar tu contraseña).
2. Click en **Add people**.
3. Buscar por su usuario de GitHub o email, y agregarlos uno por uno.
4. Cada uno va a recibir una invitación por email o notificación en GitHub que debe aceptar.

> Alternativa más prolija a futuro: crear una **Organización** gratuita en GitHub (https://github.com/organizations/new), mover el repo ahí, y manejar accesos por equipos. No es necesario para arrancar con 4 personas.

## 3. Instalar Git LFS (cada persona del equipo, una sola vez)

Descargar e instalar desde https://git-lfs.com/, y después correr en la terminal:

```
git lfs install
```

## 4. Subir el proyecto ya preparado

Desde la carpeta raíz de tu proyecto de Unity (donde están las carpetas `Assets`, `ProjectSettings`, `Packages`):

1. Copiar a esa carpeta los archivos que te dejé: `.gitignore`, `.gitattributes` y `README.md` (y `SETUP-GITHUB.md` si querés conservarlo como referencia).
2. Abrir una terminal ahí y correr:

```bash
git init
git lfs install
git add .gitattributes
git add .gitignore
git add .
git commit -m "Estructura inicial del proyecto Unity"
git branch -M main
git remote add origin https://github.com/m1000th/2DunityGame.git
git push -u origin main
```

3. Crear la rama de trabajo del equipo:

```bash
git checkout -b develop
git push -u origin develop
```

## 5. Que el resto del equipo clone el repo

Cada compañero, después de aceptar la invitación:

```bash
git clone https://github.com/m1000th/2DunityGame.git
cd 2DunityGame
git lfs install
git checkout develop
```

Y ya pueden abrir la carpeta con Unity Hub.

## 6. (Opcional pero recomendado) Proteger la rama main

En **Settings > Branches > Add branch protection rule** sobre `main`:
- Require a pull request before merging.
- Require al menos 1 aprobación.

Así nadie sube cambios directo a `main` sin que otro los revise, lo cual evita romper la versión estable por error.

## Checklist rápido

- [ ] Repo creado en GitHub (privado)
- [ ] 3 compañeros invitados como colaboradores
- [ ] Git LFS instalado por cada persona
- [ ] `.gitignore` y `.gitattributes` copiados a la raíz del proyecto Unity
- [ ] Primer commit y push a `main`
- [ ] Rama `develop` creada
- [ ] (Opcional) Protección de rama `main` activada
- [ ] En Unity: Version Control = Visible Meta Files, Asset Serialization = Force Text
