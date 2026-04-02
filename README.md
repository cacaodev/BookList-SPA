# Proyecto: BookList SPA

## Descripción del Proyecto

Este proyecto consiste en una Single Page Application (SPA) desarrollada con Vue para la Editorial Nova. El objetivo principal es modernizar la gestión de su catálogo, permitiendo registrar, visualizar y eliminar libros de forma fluida y reactiva.

## Resumen de Entregas por Lección

- Lección 1
  - Se creó la estructura base en `App.vue` utilizando el patrón MVVM.
  - Se implementó un estado inicial con datos reactivos para el nombre de usuario y un contador de visitas funcional.
- Lección 2
  - Desarrollo del componente modular `Libro.vue` para representar cada unidad del catálogo.
  - Uso de directivas `v-for` para iterar la lista, `v-bind` para el paso de datos y `v-if/v-else` para mostrar un mensaje de advertencia cuando el catálogo está vacío.
- Lección 3
  - Implementación de un formulario dinámico con `v-model` que incluye campos de texto, selección de categoría y área de descripción.
  - Visualización de datos en tiempo real para validar la reactividad del modelo.
- Lección 4
  - Uso de `@click` para la adición y eliminación de elementos en el array de libros.
  - Aplicación de modificadores como `.prevent` en el formulario para evitar recargas de página y `@keyup.enter` para mejorar la experiencia de usuario.
  - Uso del modificador `.once` para acciones de confirmación únicas.
- Lección 5
  - Configuración de Vue Router con tres rutas principales: Inicio (`/`), Catálogo (`/libros`) y Detalle (`/libros/:id`).
  - Implementación de rutas dinámicas y pasaje de parámetros mediante `props` para visualizar información específica de cada libro.

## Decisiones Tomadas

- Modularidad: Se optó por separar la lógica en componentes (`Libro.vue`) y vistas (`views/`) para asegurar que el código sea escalable y reutilizable.
- Navegación SPA: Se priorizó una navegación fluida mediante `<router-view />` para evitar recargas innecesarias y cumplir con el estándar de una aplicación moderna.
- Validación Visual: Se utilizó `v-show` en botones de acción para garantizar que el usuario solo pueda interactuar cuando los datos mínimos estén presentes.

## Instrucciones de Ejecución

Para previsualizar y trabajar en este proyecto de forma local, siga estos pasos:

1. Clonar el repositorio:
   `git clone https://github.com/cacaodev/BookList-SPA`

2. Instalar las dependencias necesarias:
   `npm install`

3. Iniciar el servidor de desarrollo:
   `npm run dev`

Nota: Si el proyecto fue configurado con Vue CLI en lugar de Vite, utilice el comando `npm run serve` para levantar el servidor.
Nota personal: Se me olvidó que tenía que hacerlo con Vue CLI y Gemini me sugirió Vite, una vez que empecé lo dejé así no más.
