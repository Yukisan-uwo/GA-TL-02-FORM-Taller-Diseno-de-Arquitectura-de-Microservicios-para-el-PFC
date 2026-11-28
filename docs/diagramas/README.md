# Diagrama de componentes del SGRA

Mantengo el diseño editable en [`c4-nivel-3.drawio`](c4-nivel-3.drawio)
y su exportación en [`c4-nivel-3.pdf`](c4-nivel-3.pdf).
Distingo este diseño propuesto de una implementación o una validación
funcional de los microservicios.

## Vistas

Organizo ambos archivos en el mismo orden:

1. **Integro los canales del SGRA:** clientes, Gateway, servicios, bases propias y mensajería.
2. **Detallo Refuerzos y sus dependencias:** componentes internos, matrícula, reservas y eventos.
3. **Detallo Identidad, Académico y Espacios:** componentes, repositorios y publicación.
4. **Detallo Notificaciones, Seguimiento y Administración:** avisos, reportes, auditoría y configuración.
5. **Distribuyo eventos sin compartir consumidores:** publicadores, intercambio y colas de RabbitMQ.

## Edición y exportación del diagrama

Abro el `.drawio` en [diagrams.net](https://app.diagrams.net/) o en Draw.io
Desktop. Edito sus formas y conectores, no el PDF.

Para actualizar la exportación:

1. Guardo el editable con el mismo nombre.
2. Selecciono **Archivo → Exportar como → PDF**.
3. Activo **Todas las páginas** y el recorte al contenido; mantengo un borde de 20.
4. Guardo el resultado como `c4-nivel-3.pdf` en esta carpeta.
5. Compruebo las cinco páginas, su orden, los textos y los conectores.

Como alternativa, desde la raíz del repositorio uso Draw.io Desktop:

```bash
drawio --export --all-pages --crop --border 20 \
  --format pdf \
  --output docs/diagramas/c4-nivel-3.pdf \
  docs/diagramas/c4-nivel-3.drawio
```

Usé el exportador de Draw.io Desktop 32.7.4 para comprobar esta exportación.
Para el comando necesito el ejecutable `drawio` disponible y un entorno gráfico;
no utilizo esta orden como garantía de ejecución en un servidor sin pantalla.

## Incorporación al informe

Distingo la **exportación del diagrama** de la **compilación LaTeX**.
Incluyo las cinco páginas del PDF desde
[`../secciones/02-arquitectura.tex`](../secciones/02-arquitectura.tex);
compilar el informe no regenera el diagrama.

Después de actualizar la exportación, compilo el informe desde `docs/`:

```bash
pdflatex -interaction=nonstopmode -halt-on-error main.tex
biber main
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
```

Para esta compilación utilizo pdfLaTeX, Biber y los paquetes indicados en
el [README principal](../../README.md#compilación-del-informe).
Obtengo `docs/main.pdf`, que no sustituyo por `docs/diagramas/c4-nivel-3.pdf`.
En Overleaf conservo las rutas del proyecto y selecciono `docs/main.tex`
como documento principal.

Si cambio el número o el orden de las vistas, ajusto también las inclusiones
de páginas en `02-arquitectura.tex`.

## Lectura y comprobación

Interpreto las flechas según la leyenda: azul para REST/HTTPS síncrono,
naranja discontinuo para AMQP/TLS asíncrono, gris para llamadas internas
y verde para SQL sobre la base propia.

Contrasto los eventos con
[`../secciones/06-comunicacion-asincronica.tex`](../secciones/06-comunicacion-asincronica.tex)
y las interfaces con la tabla de servicios antes de cerrar una revisión.
Después de recibir observaciones reales del docente, actualizo el diseño,
su exportación y los registros correspondientes; no presento esta guía como
evidencia de una revisión docente ya realizada.
