# 📅 Contador Dinámico de Eventos (Vanilla JS + LocalStorage)

Aplicación sencilla y ligera construida con JavaScript puro (Vanilla JS) que permite a los usuarios registrar eventos futuros y ver cuántos días faltan para que ocurran. La información de los eventos se guarda directamente en el navegador del usuario utilizando `localStorage`.



## ✨ Características Principales

* **Contador de Días:** Calcula y muestra automáticamente la cantidad de días restantes para la fecha del evento.
* **Persistencia de Datos:** Utiliza `localStorage` para guardar, cargar y mantener los eventos después de cerrar y reabrir el navegador.
* **Validación Simple:** Evita agregar eventos sin nombre o fecha, y previene la adición de fechas que ya han pasado.
* **Eliminación de Eventos:** Permite eliminar eventos de la lista y del almacenamiento persistente.

## 🛠️ Tecnologías Utilizadas

* **HTML5:** Estructura de la aplicación.
* **CSS3:** Estilos básicos (referenciados a `styles.css`).
* **JavaScript (Vanilla JS):** Lógica principal, manejo del DOM, cálculo de fechas y gestión del `localStorage`.

## 🚀 Cómo Empezar

Para ejecutar esta aplicación en tu entorno local, sigue estos sencillos pasos:

1.  **Clonar el Repositorio:**
    ```bash
    git clone [URL_DE_TU_REPOSITORIO]
    cd nombre-del-proyecto
    ```
2.  **Abrir el Archivo:** Simplemente abre el archivo `index.html` en tu navegador web preferido.

> **Nota:** La aplicación no requiere un servidor local para funcionar, ya que utiliza JavaScript del lado del cliente.

## ⚙️ Funcionalidad Clave en `main.js`

### 1. Persistencia de Datos (`localStorage`)

* **`save(data)`:** Guarda la matriz `events` convertida a JSON bajo la clave `"items"` en el `localStorage`.
* **`load()`:** Recupera la cadena JSON almacenada en `"items"`.
* **Inicialización:** Al cargar, la aplicación intenta parsear la cadena JSON guardada. Si no hay datos o hay un error, inicializa `events` como una matriz vacía.

### 2. Manejo de Eventos

La función central es **`renderEvents()`**. Esta función es responsable de:
* Mapear la matriz `events` para generar el HTML de cada evento.
* Actualizar el contenido del contenedor principal (`#eventsContainer`).
* Asignar el *event listener* de `click` a **cada botón de "Eliminar"** (clase `.bDelete`) para permitir la eliminación dinámica de elementos.

### 3. Lógica de Fechas

La función **`dateDiff(d)`** es crucial para el contador.

* Calcula la diferencia entre la fecha del evento (`d`) y la fecha actual (`today`).
* Devuelve la diferencia en **días** (redondeando hacia arriba con `Math.ceil`) para mostrar los días completos restantes.

## 📝 Mejoras Futuras Sugeridas

* **Validación de Formato de Fecha:** Mejorar la validación para asegurar que la fecha seleccionada sea válida (aunque el input `type="date"` ya ayuda mucho).
* **Notificaciones:** Implementar notificaciones cuando un evento está por ocurrir.
* **Vista de Calendario:** Agregar una vista real de calendario (mes/día) en lugar de solo la lista.