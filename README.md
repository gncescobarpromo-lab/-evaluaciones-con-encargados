# evaluaciones-con-encargados

Repositorio dedicado a formularios de evaluación interna con encargados (GNC Escobar y Gas Impulso). Separado de los repos operativos de raspadita/canje para no mezclar herramientas de cliente con herramientas de gestión.

**Backend único:** un solo Apps Script + una sola Google Sheet ("Registro_Evaluaciones") reciben los datos de todas las evaluaciones, sin importar qué carpeta las envíe. Ver `AppsScript_Evaluaciones.gs.txt`.

---

## Estructura

```
evaluaciones-con-encargados/
├── AppsScript_Evaluaciones.gs.txt     (código del backend, referencia)
├── cierre-raspadita-infinia-2026/
│   └── index.html                     (evaluación de cierre, junio 2026)
└── [futura-evaluacion]/
    └── index.html
```

Cada evaluación vive en su propia carpeta. GitHub Pages publica cada una en:

```
https://[usuario].github.io/evaluaciones-con-encargados/cierre-raspadita-infinia-2026/
```

## Cómo agregar una evaluación nueva

1. Copiar la carpeta `cierre-raspadita-infinia-2026/` como plantilla.
2. Renombrarla con un slug corto y sin espacios (ej. `fidelizacion-clientes-2027`).
3. Editar las preguntas dentro del `index.html` (secciones, campos `data-scale`, `textarea`, etc.).
4. Cambiar la constante `TIPO_EVALUACION` en el `<script>` a un nombre único — ese va a ser el nombre de la pestaña nueva que se crea sola en la Sheet.
5. La constante `ENDPOINT` (URL del Apps Script) se mantiene igual siempre — es el mismo backend para todas las evaluaciones.
6. Subir la carpeta al repo.

No hace falta tocar el Apps Script para evaluaciones nuevas, salvo que se necesite lógica distinta a "guardar todo lo que llega".

## Estado

| Evaluación | Carpeta | Pestaña en Sheet | Vigente |
|---|---|---|---|
| Cierre Raspadita Infinia 2026 | `cierre-raspadita-infinia-2026` | `Cierre_Raspadita_Infinia_2026` | Sí |
