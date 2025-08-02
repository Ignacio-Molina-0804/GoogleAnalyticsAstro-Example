# Astro Starter Kit: Basics

```sh
npm create astro@latest -- --template basics
```

> 🧑‍🚀 **Seasoned astronaut?** Delete this file. Have fun!

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
│   └── favicon.svg
├── src
│   ├── assets
│   │   └── astro.svg
│   ├── components
│   │   └── Welcome.astro
│   ├── layouts
│   │   └── Layout.astro
│   └── pages
│       └── index.astro
└── package.json
```

To learn more about the folder structure of an Astro project, refer to [our guide on project structure](https://docs.astro.build/en/basics/project-structure/).

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## 👀 Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).

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

## 🧩 Tecnologías principales

- [Astro](https://astro.build/)
- [Partytown](https://partytown.builder.io/)
- [Google Analytics](https://analytics.google.com/)

## 📚 Más información

- [Documentación de Astro](https://docs.astro.build)
- [Documentación de Partytown](https://partytown.builder.io/)
- [Google Analytics](https://developers.google.com/analytics)

---

¡Listo! Ahora tienes un ejemplo funcional y optimizado de Google Analytics en Astro usando Partytown.
