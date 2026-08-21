# Log2Excel - Convertidor de Logs a Excel 🚀

**Log2Excel** es una herramienta de escritorio portable para Windows diseñada para convertir archivos de registro (`.log`, `.txt`, `.csv`) a hojas de cálculo de Microsoft Excel (`.xlsx`) de forma rápida, eficiente y 100% local.

Esta aplicación cuenta con una interfaz web moderna, responsiva y con modo oscuro (desarrollada en HTML/CSS/JS) encapsulada en una aplicación nativa de Windows utilizando Python (`pywebview`) y compilada a un archivo ejecutable independiente `.exe`.

---

## 🌟 Características

- **Diseño Moderno y Premium:** Interfaz oscura y translúcida (estilo *glassmorphism*) con micro-animaciones y soporte para arrastrar y soltar (drag & drop).
- **Procesamiento de Alto Rendimiento:** Algoritmo optimizado de un solo paso (*single-pass*) que disminuye en un **66%** el uso de memoria RAM comparado con lectores tradicionales. Soporta archivos de registro de gran tamaño sin ralentizar el sistema.
- **Configuración Dinámica:**
  - Selector de separador de celdas: Punto y coma (`;`), Coma (`,`), Tabulación (`\t`), Barra vertical (`|`) o delimitador personalizado.
  - Opción para activar/desactivar detección automática de fila de encabezados.
- **Previsualización Instantánea:** Muestra las primeras 15 filas del archivo parseado antes de guardarlo para verificar que la configuración sea correcta.
- **Privacidad Total:** Todo el procesamiento y la conversión se realizan de forma local en tu computadora. Tus datos nunca se envían a ningún servidor externo.
- **100% Portable:** Un único archivo `.exe` que puedes llevar en un pendrive y usar sin necesidad de instalaciones previas de Python o Node.js.

---

## 📂 Estructura del Repositorio

El repositorio está estructurado para su uso directo:

- **[`Log2Excel.exe`](./Log2Excel.exe)**: Ejecutable portable principal para Windows en la raíz del repositorio.
- **`.gitignore`**: Configuración para evitar subir archivos basura o temporales de compilación.

---

## 🛠️ Cómo Usar

1. Descarga el archivo **`Log2Excel.exe`** directamente del repositorio.
2. Abre **`Log2Excel.exe`** en tu máquina con Windows.
3. Elige el delimitador que utiliza tu archivo log (por defecto `;`).
4. Arrastra tu archivo `.log` o `.txt` a la zona de carga (o haz clic para buscarlo).
5. Verifica la estructura en la tabla de previsualización.
6. Haz clic en **"Exportar a Excel"** para abrir el cuadro nativo de Windows y guardar tu archivo `.xlsx`.

---

## 💻 Desarrollo y Recompilación

Si deseas descargar el código fuente y modificar la aplicación en el futuro, necesitarás tener instalado **Python 3.10+**.

### 1. Requisitos
Instala las dependencias necesarias:
```powershell
pip install pywebview pyinstaller
```

### 2. Compilación a Ejecutable
Desde la carpeta raíz del proyecto original, ejecuta el siguiente comando en la consola de comandos de Windows o PowerShell para volver a compilar el código fuente a `.exe`:
```powershell
python -m PyInstaller --onefile --noconsole --add-data "index.html;." --add-data "style.css;." --add-data "app.js;." --name "Log2Excel" main.py
```
El nuevo archivo ejecutable se generará en la carpeta `dist/`.
