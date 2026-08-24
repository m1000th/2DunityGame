# [Nombre del Juego]

Proyecto de Unity desarrollado por un equipo de 4 personas.

## Requisitos

- Unity (versión: _completar con la versión exacta que usan, ej. 2022.3.XXf1 LTS_)
- Git
- [Git LFS](https://git-lfs.com/) (obligatorio, ver instrucciones abajo)

## Configuración inicial (una sola vez por persona)

1. Instalar Git LFS: https://git-lfs.com/ y después correr una vez en la terminal:
   ```
   git lfs install
   ```
2. Clonar el repo:
   ```
   git clone https://github.com/<usuario-u-org>/<nombre-repo>.git
   ```
3. Abrir la carpeta del proyecto con Unity Hub (usar la misma versión de Unity que el resto del equipo).

## Configuración recomendada dentro de Unity

En **Edit > Project Settings > Editor**:

- **Version Control > Mode**: `Visible Meta Files`
- **Asset Serialization > Mode**: `Force Text`

Esto asegura que escenas, prefabs y demás assets se guarden en formato texto (YAML) para que Git pueda mergearlos correctamente.

## Flujo de trabajo (ramas)

- `main`: versión estable, siempre debe compilar y funcionar.
- `develop`: rama de integración del equipo.
- `feature/<nombre>`: una rama por tarea/feature (ej. `feature/inventario`, `feature/menu-principal`).

Flujo sugerido:
1. Crear rama desde `develop`: `git checkout -b feature/mi-tarea`
2. Trabajar y commitear seguido, con mensajes claros.
3. Subir la rama y abrir un Pull Request hacia `develop`.
4. Que al menos otra persona del equipo lo revise antes de mergear.
5. Periódicamente, mergear `develop` a `main` cuando esté estable.

## Evitar conflictos

- Evitar que dos personas editen la **misma escena o prefab** al mismo tiempo siempre que se pueda.
- Si van a tocar la misma escena, avisar por el chat del equipo antes.
- Configurar Unity's Smart Merge como herramienta de merge para archivos `.unity` y `.prefab` (reduce mucho los conflictos feos).
