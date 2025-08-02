# Google Analytics Astro Example

Este proyecto es un ejemplo básico de cómo integrar Google Analytics en un sitio construido con [Astro](https://astro.build), utilizando la integración de [Partytown](https://partytown.builder.io/) para cargar scripts de terceros de forma optimizada.

## 🚀 ¿Cómo funciona el proyecto?

- **Astro** es el framework principal utilizado para construir el sitio.
- **Partytown** se utiliza para cargar el script de Google Analytics en un web worker, mejorando el rendimiento y evitando bloquear el hilo principal.
- El componente [`GoogleAnalytics.astro`](src/components/GoogleAnalytics.astro) incluye el código necesario para inicializar Google Analytics usando Partytown.
- El layout principal [`Layout.astro`](src/layouts/Layout.astro) importa e inserta el componente de Google Analytics en el `<head>` de todas las páginas.
- La página principal [`index.astro`](src/pages/index.astro) utiliza el layout y muestra el componente de bienvenida.

## 📦 Estructura del proyecto

```
/
├── public/
│   └── favicon.svg
├── src/
│   ├── assets/
│   ├── components/
│   │   ├── GoogleAnalytics.astro
│   │   └── Welcome.astro
│   ├── layouts/
│   │   └── Layout.astro
│   └── pages/
│       └── index.astro
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

## 🛠️ Instalación y uso

1. Instala las dependencias:
   ```sh
   npm install
   ```

2. Inicia el servidor de desarrollo:
   ```sh
   npm run dev
   ```

3. Abre [http://localhost:4321](http://localhost:4321) en tu navegador.

## 📊 ¿Cómo se integra Google Analytics?

- El archivo [`GoogleAnalytics.astro`](src/components/GoogleAnalytics.astro) contiene el script de Google Analytics, pero usando `type="text/partytown"` para que Partytown lo ejecute en un web worker.
- El layout [`Layout.astro`](src/layouts/Layout.astro) incluye este componente en el `<head>`, por lo que el código de Analytics se carga en todas las páginas que usen este layout.

## ⚠️ Importante: Configura tu GA_MEASUREMENT_ID

Para que Google Analytics funcione correctamente, debes reemplazar `GA_MEASUREMENT_ID` por el ID de medición de tu propia propiedad de Google Analytics.

Abre el archivo [`src/components/GoogleAnalytics.astro`](src/components/GoogleAnalytics.astro) y reemplaza todas las apariciones de `GA_MEASUREMENT_ID` por tu identificador real, que tiene un formato similar a `G-XXXXXXXXXX`:

```astro
<!-- Google tag (gtag.js) -->
<script type="text/partytown" async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script type="text/partytown">
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-XXXXXXXXXX');
</script>
```

Puedes encontrar tu ID de medición en la configuración de tu propiedad de Google Analytics.

## 🧩 Tecnologías principales

- [Astro](https://astro.build/)
- [Partytown](https://partytown.builder.io/)
- [Google Analytics](https://analytics.google.com/)

## 📚 Más información

- [Documentación de Astro](https://docs.astro.build)
- [Documentación de Partytown](https://partytown.builder.io/)
- [Google Analytics](https://developers.google.com/analytics)

