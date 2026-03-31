# Convertidor de Word/ODT a sitio HTML (MkDocs)

🔗 **[Ver el sitio de demostración generado](https://stahe.github.io/es-word-odt-vers-html-janv-2026/)**

---

## 📝 Descripción

El objetivo de este proyecto es poner a disposición del lector un conversor en Python de documentos Word u ODT a un sitio web HTML estático.

Cuando el documento ODT o DOCX es adecuado, el conversor genera un sitio web HTML de muy buena calidad mediante **MkDocs**.

## 🤖 Contexto de creación

Este conversor fue creado inicialmente por la IA **Gemini 3**. Es el resultado de sucesivas iteraciones para gestionar con precisión la estructura de los documentos ODT (OpenDocument Text).
Posteriormente fue mejorado por la IA **ChatGPT 5.2**, que generó el conversor para documentos Word.

## ✨ Funcionalidades

El script `convert.py` realiza las siguientes acciones:

* **Conversión de ODT/DOCX a Markdown**: Analiza el archivo de origen para extraer su estructura.
* **Gestión de títulos**: Genera automáticamente la tabla de contenidos (TOC) y la navegación lateral.
* **Bloques de código**: Detección automática de lenguajes, coloración sintáctica y **gestión precisa de la numeración de líneas** (atributos `start-value`).
* **Listas**: Compatibilidad con listas con viñetas y numeradas, anidadas y mixtas, con sangría correcta.
* **Formato**: Compatibilidad con *negrita*, *cursiva*, *subrayado* y *resaltado* (respetando los colores originales).
* **Imágenes**: Extracción e integración automática de las imágenes contenidas en el documento.
* **Enlaces**: Los hipervínculos o referencias del documento de origen se convierten en hipervínculos en el documento HTML.
* **Notas al pie**: Se gestionan las notas al pie.
* **Configuración**: Personalización mediante un archivo `config.py` (notas al pie, Google Analytics, etc.).

## 🚀 Instalación

### Requisitos previos

* Python 3.x
* Las siguientes bibliotecas:

```bash
pip install odfpy unidecode mkdocs mkdocs-material

```

### Estructura del proyecto

Asegúrate de tener los siguientes archivos:

* `convert.py`: El script de conversión.
* `config.py`: Su archivo de configuración.
* `su-documento.odt/docx`: El documento de origen.

## 💻 Uso

1. **Conversión**
Ejecute el script indicando el archivo ODT / DOCX de origen y el archivo de configuración:
```bash
python convert_odt_vxxx.py su-documento.odt config.py
python convert_docx_vxx.py su-documento.docx config.py
```


*Esto generará una carpeta `docs/` que contiene los archivos Markdown y un archivo `mkdocs.yml`.*
2. **Vista previa**
Para ver el sitio en local:
```bash
python -m mkdocs serve

```


3. **Generación**
Para compilar el sitio estático (carpeta `site/`):
```bash
python build

```


## ⚙️ Configuración (`config.py`)

El archivo `config.py` permite controlar el aspecto del sitio:

* **mkdocs**: Parámetros generales del sitio (título, descripción, tema Material).
* **footer**: Código HTML completo para personalizar el pie de página.
* **code**: Reglas de detección de lenguajes para el resaltado sintáctico.
* **extra**: Configuración de Google Analytics (GA4).

## 📄 Licencia

Este tutorial, escrito por **Serge Tahé**, se pone a disposición del público según los términos de la:
*Licencia Creative Commons Reconocimiento – Sin uso comercial – Compartir bajo las mismas condiciones 3.0 no adaptada.*
