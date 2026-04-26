# turiver_registro

Landing page de registro para [tuRiver.com](https://www.turiver.com), la comunidad online de hinchas de River Plate.

Servida en **https://registrarse.turiver.com** vía GitHub Pages.

## Qué hay acá

- `index.html` — landing estática (HTML + CSS inline, sin dependencias de build).
- `CNAME` — dominio personalizado para GitHub Pages.

## Funcionamiento

La landing es 100% estática. Los botones de registro redirigen a las rutas de autenticación públicas del foro:

| Botón | Destino |
|-------|---------|
| Google | `https://www.turiver.com/auth/google_oauth2` |
| Facebook | `https://www.turiver.com/auth/facebook` |
| Discord | `https://www.turiver.com/auth/discord` |
| Email | `https://www.turiver.com/signup?email=...` |

El campo de email del formulario se pasa como query string al endpoint `/signup` para pre-llenar el formulario del foro.

## Desarrollo local

No requiere build. Cualquier servidor estático sirve:

```bash
python3 -m http.server 8000
# o
npx serve .
```

Después abrí `http://localhost:8000`.

## Deploy

Cada push a la rama por defecto despliega automáticamente vía GitHub Pages. El dominio `registrarse.turiver.com` apunta a este repo mediante el archivo `CNAME` y un registro CNAME en el DNS.

## Contribuir

Pull requests bienvenidos. Mantené el HTML simple y sin frameworks — la idea es que cargue rápido y sin JS pesado.

## Licencia

Código abierto bajo MIT. Las marcas, escudos y referencias a River Plate son propiedad de sus respectivos dueños y se usan únicamente con fines descriptivos por parte de la comunidad de hinchas.
