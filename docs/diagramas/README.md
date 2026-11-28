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
