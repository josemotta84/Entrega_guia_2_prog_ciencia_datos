# Análisis de Deserción de Clientes en una Empresa de Telecomunicaciones

## Descripción General

Este proyecto tiene como objetivo aplicar los conceptos de Pandas en la manipulación y análisis de datos estructurados. Se trabajó con Series y DataFrames, aplicando técnicas de acceso, selección, filtrado y agregación de datos. El análisis se centra en identificar los factores clave que influyen en la deserción de clientes (churn) en una empresa de telecomunicaciones, comprendiendo patrones de comportamiento y generando estrategias efectivas para reducir la tasa de abandono.

## Descripción de las Variables del Dataset

El dataset `telecom_churn` contiene información detallada sobre clientes de una empresa de telecomunicaciones, incluyendo:

- `state`: Estado donde reside el cliente.
- `account length`: Duración de la cuenta del cliente.
- `area code`: Código de área del cliente.
- `phone number`: Número de teléfono del cliente.
- `international plan`: Indica si el cliente tiene un plan internacional.
- `voice mail plan`: Indica si el cliente tiene un buzón de voz.
- `number vmail messages`: Número de mensajes de voz.
- `total day minutes`, `total day calls`, `total day charge`: Minutos, llamadas y costos diurnos.
- `total eve minutes`, `total eve calls`, `total eve charge`: Minutos, llamadas y costos vespertinos.
- `total night minutes`, `total night calls`, `total night charge`: Minutos, llamadas y costos nocturnos.
- `total intl minutes`, `total intl calls`, `total intl charge`: Minutos, llamadas y costos internacionales.
- `customer service calls`: Número de llamadas al servicio al cliente.
- `churn`: Indica si un cliente ha desertado de la empresa (1) o sigue siendo cliente (0).

## Instrucciones del Código

1. **Exploración y Limpieza de Datos**:
    - Se importaron las librerías necesarias y se cargó el dataset `telecom_churn.csv` en un DataFrame de Pandas. Luego, se mostraron las primeras 5 filas del DataFrame para obtener una vista preliminar de los datos.
    - Se verificó la cantidad de filas y columnas del dataset para entender su tamaño.
    - Se mostró información general del dataset, incluyendo los tipos de datos de cada columna, para identificar posibles problemas con los tipos de datos.
    - Se identificaron valores nulos en las columnas para determinar si era necesario realizar alguna limpieza de datos.

2. **Análisis de Churn y Factores Relacionados**:
    - Se calculó el porcentaje de clientes que han desertado (`churn = 1`). El resultado mostró que aproximadamente el 14.5% de los clientes han desertado.
    - Se analizó la variable `international plan`, que indica si un cliente tiene un plan internacional. Se calculó la tasa de deserción entre los clientes con plan internacional y se comparó con la tasa general de deserción. El análisis reveló que el 42.4% de los clientes con plan internacional desertaron, lo que es significativamente mayor que la tasa general de deserción.
    - Se analizó la variable `voice mail plan`, que indica si un cliente tiene un buzón de voz. Se calculó la tasa de deserción entre los clientes con buzón de voz y se comparó con la tasa general de deserción. El análisis mostró que solo el 7.1% de los clientes con buzón de voz desertaron, lo que es menor que la tasa general de deserción.

3. **Análisis de la Duración del Servicio y Deserción**:
    - Se calculó la duración promedio de la cuenta (`account length`) entre los clientes que desertaron y los que permanecen. Los resultados mostraron que la duración promedio de la cuenta para los clientes que desertaron es de 103.7 días, mientras que para los que permanecen es de 101.1 días. Esto sugiere que la duración de la cuenta no tiene un impacto significativo en la deserción.
    - Se generó un histograma de la duración de la cuenta dividido por la variable `churn` para visualizar la distribución de la duración de la cuenta entre los clientes que desertaron y los que permanecen. El histograma mostró que no hay una diferencia notable en la distribución de la duración de la cuenta entre los dos grupos.

4. **Relación entre Deserción y Uso del Servicio**:
    - Se comparó la cantidad de minutos usados en llamadas diurnas (`total day minutes`) entre los clientes que desertaron y los que permanecen. Los resultados mostraron que los clientes que desertaron usaron en promedio 206.9 minutos diurnos, mientras que los que permanecen usaron 175.2 minutos. Esto sugiere que los clientes que usan más minutos diurnos tienen una mayor probabilidad de deserción.
    - Se comparó la cantidad de minutos usados en llamadas nocturnas (`total night minutes`) entre los clientes que desertaron y los que permanecen. Los resultados mostraron que los clientes que desertaron usaron en promedio 205.2 minutos nocturnos, mientras que los que permanecen usaron 200.1 minutos. Esto sugiere que el uso nocturno del servicio no tiene un impacto significativo en la deserción.
    - Se comparó el número total de llamadas diurnas (`total day calls`) entre los clientes que desertaron y los que permanecen. Los resultados mostraron que los clientes que desertaron realizaron en promedio 101.7 llamadas diurnas, mientras que los que permanecen realizaron 100.1 llamadas. Esto sugiere que la cantidad de llamadas diurnas no tiene un impacto significativo en la deserción.

5. **Impacto de las Llamadas al Servicio al Cliente en la Deserción**:
    - Se calculó el número promedio de llamadas al servicio al cliente (`customer service calls`) entre los clientes que desertaron y los que permanecen. Los resultados mostraron que los clientes que desertaron realizaron en promedio 2.2 llamadas al servicio al cliente, mientras que los que permanecen realizaron 1.4 llamadas. Esto sugiere que los clientes que llaman más al servicio al cliente tienen una mayor probabilidad de deserción.
    - Se creó una nueva variable `many_service_calls` que indica si un cliente ha llamado más de 3 veces al servicio al cliente. Esto permitió dividir a los clientes en dos grupos para un análisis más detallado.
    - Se comparó la tasa de deserción entre los clientes que llamaron más de 3 veces al servicio al cliente y los que llamaron 3 veces o menos. Los resultados mostraron que el 50% de los clientes que llamaron más de 3 veces desertaron, mientras que solo el 11.8% de los clientes que llamaron 3 veces o menos desertaron. Esto sugiere que la frecuencia de llamadas al servicio al cliente está fuertemente relacionada con la deserción.

6. **Análisis del Costo de las Llamadas y Churn**:
    - Se comparó el costo total de llamadas diurnas (`total day charge`) entre los clientes que desertaron y los que permanecen. Los resultados mostraron que los clientes que desertaron tuvieron un costo promedio de $35.5 en llamadas diurnas, mientras que los que permanecen tuvieron un costo promedio de $29.8. Esto sugiere que los clientes con mayores costos en llamadas diurnas tienen una mayor probabilidad de deserción.
    - Se comparó el costo total de llamadas nocturnas (`total night charge`) entre los clientes que desertaron y los que permanecen. Los resultados mostraron que los clientes que desertaron tuvieron un costo promedio de $9.2 en llamadas nocturnas, mientras que los que permanecen tuvieron un costo promedio de $9.0. Esto sugiere que el costo de las llamadas nocturnas no tiene un impacto significativo en la deserción.
    - Se comparó el costo total de llamadas internacionales (`total intl charge`) entre los clientes que desertaron y los que permanecen. Los resultados mostraron que los clientes que desertaron tuvieron un costo promedio de $2.7 en llamadas internacionales, mientras que los que permanecen tuvieron un costo promedio de $2.6. Esto sugiere que el costo de las llamadas internacionales no tiene un impacto significativo en la deserción.


