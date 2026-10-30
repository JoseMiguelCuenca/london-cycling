# Santander Cycles · Londres

PEC2 de Visualización de Datos — José Miguel Cuenca Fernández.

## Objetivo
Describir el uso registrado de Santander Cycles del 1 al 14 de agosto de 2024 mediante una infografía de estudio de la demanda, en la misma infografía se añaden diagramas de cuerdas comparativo y un ridgeline. Los viajes no equivalen a personas únicas ni permiten medir demanda no atendida.

Información de cada visualización:
Volumen y actividad horaria

La distinción por tipo de día y la normalización por número de jornadas son buenas decisiones. Comprobaría que los ejes y las unidades expresan claramente cuándo hablamos de viajes totales y cuándo de viajes medios diarios.












Diagramas de cuerdas

Son adecuados para explorar conexiones territoriales, pero no siempre facilitan la comparación exacta. Mantendría ambos y añadiría una frase más explícita sobre la diferencia de 7,25 puntos porcentuales de viajes internos entre semana y fin de semana.












Ridgeline de duración

Es una buena elección para comparar distribuciones. Ya aclaras que las curvas están normalizadas. Resaltaría las medianas y comprobaría que la exclusión de viajes fuera del intervalo de 1–120 minutos queda suficientemente visible.

## Visualizaciones
- Infografía: https://josemiguelcuenca.github.io/london-cycling/
- Volumen diario: https://public.flourish.studio/visualisation/30743491/
- Perfil horario: https://public.flourish.studio/visualisation/30745721/
- Chord entre semana: https://public.flourish.studio/visualisation/30743288/
- Chord fin de semana: https://public.flourish.studio/visualisation/30743390/
- Ridgeline: https://josemiguelcuenca.github.io/london-cycling/assets/ridgeline_duracion.svg
## Datos y metodología
411.370 viajes. Preparación y análisis realizados en Python; gráficos interactivos en Flourish. Las cifras diarias y horarias incluyen todos los registros que superan las comprobaciones iniciales. Promedios sobre 10 días entre semana y 4 de fin de semana.

La unión con el inventario geográfico de TfL de 2023 utiliza nombres normalizados y revisiones documentadas. Se corrigen dos inconsistencias de coordenadas mediante Easting/Northing. Se asignan distritos mediante unión espacial con límites administrativos. 794 estaciones localizadas en 12 distritos permiten localizar ambos extremos de 403.095 viajes (97,99 %). Se conservan viajes internos y entre distritos.

El ridgeline usa 404.340 viajes de 1–120 minutos (98,29 %), histogramas suavizados con una ventana gaussiana de 1,5 minutos y densidades normalizadas por grupo. No muestra volumen absoluto. Los resultados no deben extrapolarse al año completo.

## Fuentes
- Viajes: https://cycling.data.tfl.gov.uk/ — 401JourneyDataExtract01Aug2024-14Aug2024.csv.
- Inventario: https://tfl.gov.uk/corporate/transparency/freedom-of-information/foi-request-detail?referenceId=FOI-3468-2223
- Distritos: https://data.london.gov.uk/dataset/london-boroughs-e55pw
- Condiciones TfL: https://tfl.gov.uk/corporate/terms-and-conditions/transport-data-service

Powered by TfL Open Data. Los datos de terceros conservan sus condiciones originales; este repositorio no les atribuye una licencia nueva.

## Estructura
Notebooks- `01_exploracion.ipynb`: preparación y análisis (incorporar el notebook local).
`data/processed/`: tablas agregadas exportadas (incorporar CSV locales).
`docs/`: página pública y ridgeline.
Los datos originales se obtienen de las fuentes; no es necesario subirlos para mostrar la web.

## Publicación
Subir la carpeta docs conservando su estructura. En Settings → Pages seleccionar Deploy from a branch, main y /docs. La dirección prevista es https://JoseMiguelCuenca.github.io/london-cycling/ una vez completada la publicación.
