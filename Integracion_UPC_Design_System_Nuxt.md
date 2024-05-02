# Integración de UPC Design System en Nuxt

## Paso 1: Instalar la biblioteca

Abre una terminal y ejecuta el siguiente comando para instalar `upc-design-system`:

```bash
npm install upc-design-system
```

## Paso 2: Crear el plugin

Crea un archivo `upc-design-system.js` en la carpeta `plugins` con el siguiente contenido:

```javascript
// plugins/upc-design-system.js
import { defineNuxtPlugin } from "#app";
import designsystem from "upc-design-system/dist/upc-design-system.ssr";
import "upc-design-system/dist/style.css";

export default defineNuxtPlugin((nuxtApp) => {
  nuxtApp.vueApp.use(designsystem);
});
```

## Paso 3: Configurar Nuxt para usar el plugin

Añade la referencia al plugin en el archivo `nuxt.config.ts`:

```typescript
// nuxt.config.ts
import { defineNuxtConfig } from 'nuxt'

export default defineNuxtConfig({
  devtools: { enabled: false },
  plugins: ["~/plugins/upc-design-system.js"],
});
```

## Paso 4: Ejecutar tu aplicación

Ejecuta tu aplicación Nuxt en modo de desarrollo con el siguiente comando:

```bash
npm run dev
```
