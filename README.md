# FrontEndStore - Inicio

Este es un proyecto de tienda en línea basado en HTML y CSS. Incluye estilos personalizados, responsive design y un pipeline de CI/CD con GitHub Actions.

## Despliegue Automático (CI/CD con GitHub Actions)

Este proyecto usa `peaceiris/actions-gh-pages` para desplegar automaticamente a GitHub Pages.

### Flujo de trabajo (`.github/workflows/deploy.yml`):

1. **Validación HTML y CSS:**
   - `htmlhint`: Valida el HTML.
   - `stylelint`: Valida los estilos CSS.

2. **Build & Deploy:**
   - Usa GitHub Actions para crear un commit y hacer `push` a la rama `gh-pages`.

### Requisitos para el despliegue:

- El repositorio **debe estar público**.
- En **Settings > Pages**, selecciona `gh-pages` como rama de despliegue.
- Necesitas configurar correctamente el **token de autenticación** para el bot (ver solución más abajo si ves error 403).

## Cómo contribuir

1. Haz un fork del repositorio.
2. Crea una rama con tu nueva funcionalidad: `git checkout -b nueva-funcionalidad`
3. Haz tus cambios y commitea: `git commit -m "Agrega nueva funcionalidad"`
4. Push a tu rama: `git push origin nueva-funcionalidad`
5. Crea un Pull Request.

### Convenciones de código:

- HTML debe seguir [HTMLHint](https://htmlhint.com/docs/user-guide/) con la configuración por defecto.
- CSS debe cumplir con [Stylelint Standard](https://github.com/stylelint/stylelint-config-standard).

---

## Cómo correr validaciones localmente

Instala dependencias:

```bash
npm install

htmlhint **/*.html

npx stylelint "**/*.css"
```
## Solución al error 403 en GitHub Actions
Si ves este error:
  `remote: Permission to USER/REPO.git denied to github-actions[bot].`
  
Solución:

- Ve a Settings > Actions > General
- Baja hasta Workflow permissions
- Activa Read and write permissions
- Guarda los cambios
