# Documentación del Componente UpcButton en Vue 3

## Estructura del Componente

```vue
<script setup lang="ts">
const args = {
  id: "button",
  currentClass: "",
  disabled: false,
  buttonType: 'primary',
  size: 'medium',
  icon: true,
  text: "Button/default",
  type: "submit",
};
const onClick = () => {
  alert("Button clicked");
};
</script>

<template>
  <div>
    <div class="flex items-center justify-center" style="height: 80vh;">
      <UpcButton v-bind="args" @click="onClick">
        <template #icon="{size, fill}">
          <UpcIconNavArrowDown :size="size" :fill="fill" />
        </template>
      </UpcButton>
    </div>
  </div>
</template>
```

## Descripción de los Elementos

### Script Setup
El bloque `<script setup lang="ts">` utiliza TypeScript y la API `setup` de Vue 3, ofreciendo una sintaxis más concisa para definir componentes.

- **`args`**: Objeto con las propiedades del `UpcButton`:
  - `id`: Identificador del botón.
  - `currentClass`: Clase CSS para estilos personalizados.
  - `disabled`: Booleano para habilitar o deshabilitar el botón.
  - `buttonType`: Estilo del botón ('primary' o 'secondary').
  - `size`: Tamaño del botón ('medium' o 'large').
  - `icon`: Indica si el botón incluye un icono.
  - `text`: Texto del botón.
  - `type`: Tipo del botón ('submit' | 'reset' | 'button').

- **`onClick`**: Función para manejar clics en el botón, mostrando una alerta.

### Template
Define la estructura HTML del componente con Flexbox para centrar el botón.

- **`<UpcButton>`**: Botón de `upc-design-system`, con propiedades pasadas por `args` y asociado al evento `onClick`.

- **Slot `icon`**:
  - Define un slot para personalizar el icono del botón, con parámetros `size` y `fill`.
  - Utiliza el token del icono en este ejemplo se utiliza el `<UpcIconNavArrowDown>`, que recibe `size` y `fill` como props.

## Uso del Componente

Este componente es ideal para interfaces que requieren un botón con funcionalidades y estética definidas por `upc-design-system`. Facilita la adaptabilidad y modularidad en aplicaciones Vue 3.
