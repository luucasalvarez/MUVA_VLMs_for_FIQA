# Memoria

Primera estructura basada en `../Contexto/Plnateamiento.md` y adaptada de `../Plantilla_Latex/tfg.tex`.

Abre la carpeta del repositorio en VS Code y `memoria.tex` como documento principal en LaTeX Workshop. Los archivos de `secciones/` contienen los cuatro bloques del planteamiento, con objetivos de redacción marcados como **Pendiente**. Los datos de autor, profesor y curso se editan en `configuracion.tex`.

Se conserva la identidad visual de la plantilla (logo, portada, colores de enlaces, geometría y estilo IEEE de bibliografía), adaptando la clase `report` a `article` para la extensión prevista de unas 15 páginas. Se eliminan los ejemplos de TFG, agradecimientos, apéndices y páginas en blanco. La extensión de este borrador no representa la memoria final.

## Compilación

Desde esta carpeta, con una distribución LaTeX instalada:

Las extensiones de VS Code no incluyen el compilador: se necesita MiKTeX o TeX Live. Tras instalarlo, reinicia VS Code para que reconozca el nuevo `PATH`. La configuración compartida en `../.vscode/settings.json` usa PDFLaTeX directamente, sin requerir Perl o latexmk. En LaTeX Workshop, selecciona la receta `PDFLaTeX (borrador sin citas)`; cuando haya citas, selecciona `PDFLaTeX y BibTeX (con citas)`.

```powershell
pdflatex -interaction=nonstopmode -halt-on-error memoria.tex
pdflatex -interaction=nonstopmode -halt-on-error memoria.tex
```

Cuando se añadan referencias y citas a `bibliografia.bib`, ejecutar:

```powershell
pdflatex -interaction=nonstopmode -halt-on-error memoria.tex
bibtex memoria
pdflatex -interaction=nonstopmode -halt-on-error memoria.tex
pdflatex -interaction=nonstopmode -halt-on-error memoria.tex
```

El borrador no incluye resultados ni referencias científicas aún verificadas. El artículo indicado en el contexto debe comprobarse antes de citarlo; el intento de consulta del enlace de arXiv no permitió recuperar su contenido.

Los recursos necesarios están copiados en esta carpeta: la memoria no depende de la carpeta ignorada `Plantilla_Latex`. La licencia de la plantilla se conserva en `LICENSE-plantilla.txt`.
