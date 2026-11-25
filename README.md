# GA-TL-02 — Taller de diseño de arquitectura de microservicios

Diseño de una arquitectura de microservicios para el Sistema de Gestión de Refuerzos Académicos (SGRA).

## Integrantes
- Zambrano Parraga Luis Mario
- Mera Jumbo Allison Michelle
- Calderon Saltos Joseph Alexander
- Garcia Sangoquiza Roger Steven

## Compilación del informe
Desde `docs/`, con TeX Live o MiKTeX que incluya pdfLaTeX, Biber, babel (español), biblatex, biblatex-ieee, booktabs, longtable, geometry, graphicx, hyperref y pdflscape:

```powershell
cd docs
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

El archivo resultante es `docs/main.pdf`. El diagrama editable y su exportación se guardarán en `docs/diagramas/`. Las evidencias fotográficas irán en `evidencias/` y las decisiones de arquitectura en `docs/adr/`.

## Estado
Estructura inicial. El diseño y las evidencias se completarán con los aportes del equipo y la revisión en clase.
