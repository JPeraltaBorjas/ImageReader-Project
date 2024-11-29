# ImageReader Project

## Descripción del Proyecto
El **ImageReader Project** es una herramienta desarrollada en Python que permite leer imágenes que contienen texto (como documentos escaneados) y convertir ese contenido en un archivo Word (.docx). Esto es especialmente útil para digitalizar documentos, extraer información de imágenes, o procesar datos de manera automatizada.

El proyecto utiliza técnicas de reconocimiento óptico de caracteres (OCR) para identificar y extraer texto de imágenes, aprovechando la potencia de librerías como `pytesseract` y `python-docx`.

---

## Características
- **Reconocimiento de texto:** Extrae texto desde imágenes en formatos como `.png`, `.jpg`, `.jpeg`, entre otros.
- **Conversión a Word:** Guarda el texto extraído en archivos `.docx` de forma automática.
- **Fácil integración:** Simple de usar y personalizar para distintas aplicaciones.
- **Compatibilidad multiplataforma:** Funciona en Windows, macOS y Linux.

---

## Instalación
1. **Clona este repositorio:**
   ```bash
   git clone https://github.com/JPeraltaBorjas/ImageReader-Project.git
   cd ImageReader-Project
   ```

2. **Instala los requisitos:**
   Asegúrate de tener Python 3.7 o superior y usa `pip` para instalar las dependencias:
   ```bash
   pip install -r requirements.txt
   ```

3. **Instala Tesseract OCR:**
   - **Windows:**
     Descarga el instalador desde [https://github.com/UB-Mannheim/tesseract/wiki](https://github.com/UB-Mannheim/tesseract/wiki) y sigue las instrucciones.
   - **Linux:**
     ```bash
     sudo apt update
     sudo apt install tesseract-ocr
     ```
   - **macOS:**
     Usa Homebrew:
     ```bash
     brew install tesseract
     ```

4. **Configura Pytesseract:**
   Asegúrate de que `pytesseract` pueda encontrar la ruta al ejecutable de Tesseract. Por ejemplo, en Windows:
   ```python
   pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'
   ```

---

## Uso
1. **Ejecuta el script principal:**
   ```bash
   python main.py
   ```
2. **Proporciona la ruta a una imagen de documento:**
   El programa leerá la imagen y generará un archivo Word con el texto extraído.

---

## Ejemplo
**Entrada:** Una imagen con texto, como:

![Ejemplo de entrada](content-project-4\Esto_es_un_texto.png)

**Salida:** Un archivo Word (`documento.docx`) con el texto:
```
Ésto es un texto
```

---

## Librerías Utilizadas
- [**pytesseract**](https://github.com/madmaze/pytesseract): Para realizar el OCR en imágenes.
- [**python-docx**](https://python-docx.readthedocs.io/): Para generar documentos Word.
- [**Pillow**](https://python-pillow.org/): Para trabajar con imágenes en Python.
- **os** y **sys**: Para gestionar rutas y configuraciones del sistema.

---

## Ejemplo de Código
A continuación, un fragmento básico del código utilizado:

```python
import pytesseract
from PIL import Image
from docx import Document

# Configuración de Tesseract
pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'

# Cargar la imagen
image_path = "ruta/a/imagen.png"
image = Image.open(image_path)

# Extraer texto de la imagen
texto = pytesseract.image_to_string(image)

# Guardar texto en un archivo Word
document = Document()
document.add_paragraph(texto)
document.save("documento.docx")

print("Texto extraído y guardado en 'documento.docx'")
```

---

## Contribuciones
¡Las contribuciones son bienvenidas! Si deseas mejorar este proyecto o agregar nuevas características, crea un *fork* del repositorio y abre un *pull request* con tus cambios.

---

## Licencia
Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo `LICENSE` para más información.

---

## Contacto
Creador: [JPeraltaBorjas](https://github.com/JPeraltaBorjas)  
Si tienes preguntas o comentarios, ¡no dudes en contactarme!

---
