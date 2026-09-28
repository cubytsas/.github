# cubytsas/.github

Perfil público y archivos compartidos de la organización Cubyt en GitHub.

| Ruta | Qué es |
| --- | --- |
| `profile/README.md` | Lo que se muestra en [github.com/cubytsas](https://github.com/cubytsas). |
| `profile/assets/` | Logo en versión clara y oscura para el perfil. |
| `SECURITY.md` | Política de seguridad por defecto para todos los repositorios de la organización. |
| `.github/workflows/npm-publish.yml` | Workflow reutilizable para publicar paquetes en npm. |

## Publicar un paquete en npm

Desde el repositorio del paquete, con el secreto `NPM_TOKEN` configurado:

```yaml
name: Publish

on:
  release:
    types: [published]

jobs:
  publish:
    uses: cubytsas/.github/.github/workflows/npm-publish.yml@main
    with:
      package-directory: .
    secrets:
      NPM_TOKEN: ${{ secrets.NPM_TOKEN }}
```

El workflow valida el contenido con `npm pack --dry-run` y publica con acceso público.
