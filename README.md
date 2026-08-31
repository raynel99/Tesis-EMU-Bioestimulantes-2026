# Market Share Analysis — Mercado de Bioestimulantes en Chile

Modelo de participación de mercado (MCI — Multiplicative Competitive Interaction, log-lineal)
aplicado al mercado chileno de bioestimulantes agrícolas: ~200 productos, 23 empresas, 5 categorías.

> Proyecto derivado de mi tesis del Magíster en Administración de Empresas Agroalimentarias
> (Pontificia Universidad Católica de Chile).

## Pregunta de negocio

¿Qué explica mejor la participación de mercado de un producto bioestimulante:
el **precio** o el **prestigio de marca**? ¿Varía esto entre categorías de producto?

## Resumen de hallazgos

- El prestigio de marca domina sobre el precio como driver de market share en casi todas
  las categorías analizadas.
- La sensibilidad al precio es significativa únicamente en la categoría Inductor.
- *(Completar con cifras finales de R², MAPE, F-statistic por categoría al migrar el modelo)*

## Metodología

1. **Recolección de datos**: dosis y precios de decenas de productos bioestimulantes
   de empresas como ADAMA, AgroAdvance, AgroConnexion, Stoller, Bayer y UPL.
2. **Construcción de variables**: variable de prestigio (escala ordinal de 4 niveles,
   ajustada a nivel de producto), transformaciones log-centradas.
3. **Modelo MCI log-lineal**: estimado originalmente en Excel (LINEST); en este repo se
   migra a Python (statsmodels) para reproducibilidad.
4. **Enfoques alternativos evaluados**: equilibrio de Nash, Monte Carlo, minimización de
   SSE vía Solver — documentados como comparación metodológica.
5. **Diagnóstico del modelo**: R², VIF, MAPE, significancia F.

## Estructura del repositorio

```
├── data/
│   ├── raw/            # Datos originales (o muestra/anonimizados si aplica confidencialidad)
│   └── processed/       # Datos limpios y listos para modelar
├── notebooks/            # Notebooks de exploración y modelado (numerados en orden de flujo)
├── src/                   # Código modular reutilizable (limpieza, features, modelo, gráficos)
├── reports/
│   └── figures/          # Gráficos exportados para el README / presentación
└── docs/                  # Notas metodológicas, glosario de variables, referencias
```

## Cómo reproducir

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

*(Instrucciones de ejecución de notebooks/scripts — completar cuando el código esté migrado)*

## Limitaciones y próximos pasos

- *(Completar: tamaño de muestra por categoría, supuestos del modelo, generalización a otros mercados)*
- Crear las siguientes subtareas ademas de añadir una visualizacion de los datos que estamos trabajando
  - Primero es crear el programa de python para estructurar mejor los datos
- Incorporar una forma de modificar los datos de forma sencilla para poder generar modificaciones personalizadas
- Concluir con una presentacion completa a nivel marketing

## Autor

Felipe — Magíster en Administración de Empresas Agroalimentarias, PUC Chile.
