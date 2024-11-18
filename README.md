Propósito del Código
Este programa es una aplicación gráfica en Python diseñada para convertir imágenes en formatos específicos compatibles con Nintendo Switch. Tiene tres funciones principales para redimensionar y ajustar imágenes según los tipos seleccionados:

ICONOS: Redimensiona las imágenes a 192x192 píxeles, con un tamaño de archivo de exactamente 147,512 bytes.
BOOTLOGO: Redimensiona las imágenes a 720x1280 píxeles (o las rota si están horizontales), con un tamaño de archivo de exactamente 3,686,470 bytes.
BACKGROUND: Redimensiona las imágenes a 1280x720 píxeles, con un tamaño de archivo de exactamente 3,686,470 bytes, sin rotación.
Además, incluye un logotipo y tu nombre como firma personal en la ventana.

Estructura del Código
Bibliotecas Importadas
os: Para manejar rutas y operaciones en el sistema de archivos.
tkinter: Para la interfaz gráfica (ventana, botones, etiquetas).
Pillow: Para manipular imágenes (abrir, redimensionar, convertir, guardar).
Funciones Principales
a. open_file
Abre un cuadro de diálogo para seleccionar una imagen.
Actualiza una etiqueta para mostrar la ruta del archivo seleccionado.
b. save_file
Abre un cuadro de diálogo para seleccionar una carpeta donde guardar la imagen ajustada.
Actualiza una etiqueta para mostrar la ruta de la carpeta seleccionada.
c. convert_image
Realiza el procesamiento de la imagen según el tipo seleccionado (ICONOS, BOOTLOGO o BACKGROUND):
Verifica que los caminos de archivo y carpeta sean válidos.
Determina las dimensiones, tamaño en bytes y ruta de salida según el tipo.
Usa Pillow para:
Abrir la imagen original.
Redimensionarla a las dimensiones requeridas.
Convertirla al modo RGBA (profundidad de color de 32 bits).
Si es BOOTLOGO y la imagen es horizontal, la rota 90°.
Guarda la imagen en formato BMP.
Ajusta el tamaño exacto del archivo rellenando con bytes 0x00 si es necesario.
Muestra un mensaje de éxito con la ubicación y tamaño final del archivo.
d. Interfaz gráfica
Tipo de conversión:
Usa botones de radio (Radiobutton) para seleccionar entre los tres tipos de conversión.
Selección de archivo:
Botón para seleccionar la imagen de entrada.
Carpeta de destino:
Botón para seleccionar dónde guardar la imagen procesada.
Botón de conversión:
Ejecuta la función de conversión.
Logo y nombre:
Muestra un logotipo redimensionado y tu nombre en la parte inferior.
Interacción con el Usuario
Selecciona el tipo de conversión.
Carga una imagen y selecciona una carpeta para guardar.
Presiona el botón CONVERTIR.
La aplicación procesa la imagen y muestra un mensaje de éxito o error.
Detalles Técnicos
Ajuste de tamaño exacto:
Verifica el tamaño del archivo generado.
Si es menor al requerido, rellena con bytes 0x00 hasta alcanzar el tamaño exacto.
Rotación automática:
En BOOTLOGO, si la imagen es más ancha que alta, la rota para que cumpla con las especificaciones.
Interfaz de Usuario
La ventana incluye:

Botones:
Selección de archivo, carpeta de destino, y conversión.
Opciones de conversión:
Tres botones de radio para elegir el tipo de imagen.
