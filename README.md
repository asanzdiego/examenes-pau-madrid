# Exámenes PAU Madrid

Repositorio con exámenes, modelos y soluciones en PDF de varias asignaturas de la PAU de Madrid, organizados por materia.

El contenido está recopilado principalmente desde [páginas de la UC3M](https://www.uc3m.es/pruebasacceso/modelos-examenes) y preparado para dos usos:

- consultar los PDFs por asignatura y curso;
- generar un PDF recopilatorio por carpeta con índice inicial.

## Asignaturas incluidas

- [filosofia](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/filosofia)
- [fisica](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/fisica)
- [ingles](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/ingles)
- [lengua](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/lengua)
- [matematicas](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/matematicas)
- [quimica](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/quimica)
- [tecnologia](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/tecnologia)

Cada carpeta contiene PDFs de distintos cursos académicos, normalmente entre `2017-2018` y `2025-2026`, según la asignatura.

## Estructura del repositorio

En la raíz:

- `descargar_pdfs_uc3m.ipynb`: cuaderno para recorrer varias páginas de la UC3M, detectar enlaces a PDF o Google Drive, descargar los archivos y generar informes.
- `concatena_pdfs_con_indice.ipynb`: cuaderno para leer los `imprimir.md` de cada asignatura, concatenar los PDFs indicados y crear un PDF final con índice y marcadores.
- `pdf_uc3m/`: informes globales de descarga (`informe_global_descargas.json` y `informe_global_descargas.csv`).

En cada carpeta de asignatura hay:

- PDFs de exámenes modelo, convocatorias ordinarias, extraordinarias, todas con sus soluciones.
- `imprimir.md`: listado ordenado de PDFs a incluir en el recopilatorio de la asignatura. Las líneas comentadas con `#` quedan excluidas.
- `mv.sh`: script auxiliar para renombrar archivos descargados y normalizar nombres o corregir problemas de codificación.
- `informe_descargas.json` y `informe_descargas.csv`: trazas de descarga por asignatura.
- un PDF final con el nombre de la carpeta:
    - [filosofia.pdf](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/filosofia/filosofia.pdf)
    - [fisica.pdf](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/fisica/fisica.pdf)
    - [ingles.pdf](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/ingles/ingles.pdf)
    - [lengua.pdf](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/lengua/lengua.pdf)
    - [matematicas.pdf](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/matematicas/matematicas.pdf)
    - [quimica.pdf](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/quimica/quimica.pdf)
    - [tecnologia.pdf](https://github.com/asanzdiego/examenes-pau-madrid/tree/main/tecnologia/tecnologia.pdf)

## Convención del contenido

Los nombres de archivo siguen una pauta bastante uniforme, por ejemplo:

- `2025-2026 Modelo examen Matematicas II.pdf`
- `2024-2025 Ordinaria Soluciones Fisica.pdf`
- `2024-2025 Extraordinaria Soluciones Lengua Castellana y Literatura II.pdf`

También aparecen variantes como:

- `coincidencias`
- `Lunes`, `Martes`
- `9_30 horas`, `12_00 horas`
- `Criterios de Correccion Generales`

## Flujo de trabajo sugerido

### 1. Descargar o actualizar documentos

Usar `descargar_pdfs_uc3m.ipynb`.

Ese cuaderno:

- define las páginas fuente por asignatura;
- descarga PDFs directos y enlaces de Google Drive;
- guarda los documentos en su carpeta correspondiente;
- genera informes por asignatura y un informe global.

### 2. Normalizar nombres

Si tras la descarga aparecen nombres extraños o problemas de acentos/codificación, revisar los `mv.sh` de cada carpeta y ejecutar los renombrados necesarios.

### 3. Seleccionar documentos para impresión o compilación

Editar `imprimir.md` dentro de cada asignatura para decidir:

- qué PDFs incluir;
- en qué orden;
- cuáles dejar comentados temporalmente.

### 4. Generar recopilatorios

Usar `concatena_pdfs_con_indice.ipynb`.

Ese cuaderno:

- recorre las subcarpetas con `imprimir.md`;
- concatena los PDFs en el orden indicado;
- genera un PDF final por asignatura;
- añade un índice inicial y marcadores internos.

## Dependencias

Los cuadernos instalan dependencias automáticamente si faltan. Se usan al menos estas librerías:

- `requests`
- `beautifulsoup4`
- `pandas`
- `pypdf`
- `reportlab`

## Observaciones

- Algunos nombres de archivo conservan huellas de problemas de codificación originales, y por eso existen scripts `mv.sh`.
- No todas las asignaturas tienen exactamente el mismo número de documentos ni la misma cobertura por curso.
