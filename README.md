# FORM-IC-01 — Investigación Individual

Investigación sobre la arquitectura orientada a eventos en LinkedIn y su aplicación al Sistema de Gestión de Refuerzo Académico (SGRA), para la asignatura Aplicaciones Distribuidas.

**Estudiante:** Toaquiza Zambrano Belinda Betzabeth.

**Repositorio público:** https://github.com/BelindaTZ/FORM-IC-01

## Archivos

- `doc/main.tex`: archivo principal del documento.
- `doc/datos-portada.tex` y `doc/portada.tex`: datos y diseño de la carátula.
- `doc/secciones/`: análisis del caso, aplicación al SGRA y declaración de uso de inteligencia artificial.
- `doc/referencias.bib`: referencias bibliográficas en formato BibLaTeX, presentadas con estilo IEEE.
- `doc/main.pdf`: PDF compilado, con portada, una página de análisis y una página con referencias y declaración de IA.
- `evidencia/linkedin-retraso-procesamiento-lotes.png`: captura de la fuente principal con el fragmento resaltado sobre el retraso de 24 a 48 horas. La captura se conserva por separado del PDF.

## Compilación

**Compilador:** pdfLaTeX. **Procesador de bibliografía:** Biber. **Archivo principal:** `doc/main.tex`.

Se necesita una distribución de LaTeX, como MiKTeX o TeX Live, con pdfLaTeX y Biber instalados y disponibles en la terminal.

Desde la raíz del repositorio, entrar en `doc` y ejecutar los comandos en este orden: **pdflatex → biber → pdflatex → pdflatex**.

```sh
cd doc
pdflatex -interaction=nonstopmode -halt-on-error main.tex
biber main
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
```

El resultado se guarda como `doc/main.pdf`. Las dos pasadas finales resuelven las citas y referencias del documento.

## Dependencias de LaTeX

- Clase `article` y paquetes `inputenc`, `fontenc`.
- `babel`, con soporte para español.
- `newtxtext` y `newtxmath`, para las fuentes de texto y matemáticas.
- `geometry`, para los márgenes y el tamaño A4.
- `setspace`, `tabularx` y `array`.
- `csquotes`.
- `biblatex`, `biblatex-ieee` y Biber, para las referencias IEEE.
- `hyperref`, para los enlaces del documento.

MiKTeX puede solicitar instalar los paquetes que falten durante la primera compilación. En TeX Live, deben estar disponibles los paquetes anteriores y sus dependencias.

Los archivos auxiliares de compilación, los logs y las vistas previas temporales se excluyen mediante `.gitignore`. El PDF final sí se incluye en el repositorio.
