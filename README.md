🔹 Introducción

La evasión de clientes (Churn) es uno de los principales desafíos en el sector de telecomunicaciones, ya que la pérdida de clientes impacta directamente en los ingresos y la sostenibilidad del negocio. El objetivo de este análisis es identificar patrones y factores asociados a la evasión de clientes en Telecom X, utilizando técnicas de análisis de datos para comprender el comportamiento de los usuarios y apoyar la toma de decisiones estratégicas orientadas a la retención.

A través del análisis de datos demográficos, servicios contratados, información contractual y cargos económicos, se busca responder a la pregunta clave: ¿Qué características aumentan la probabilidad de que un cliente cancele el servicio?

🔹 Limpieza y Tratamiento de Datos Importación de datos

Los datos fueron cargados directamente desde una API en formato JSON alojada en GitHub.

Se utilizó pandas para convertir el JSON en un DataFrame.

Debido a que los datos estaban anidados, se aplicó pd.json_normalize() para aplanar la estructura.

Tratamiento y corrección de inconsistencias

Se realizaron las siguientes acciones clave:

✔️ Conversión de la variable account_Charges_Total a tipo numérico usando pd.to_numeric, corrigiendo errores de formato.

✔️ Reemplazo de valores nulos resultantes por 0, coherente con clientes nuevos (tenure = 0).

✔️ Normalización de categorías inconsistentes como:

"No internet service" → "No"

"No phone service" → "No"

✔️ Eliminación de espacios en blanco en variables categóricas.

✔️ Verificación de duplicados, asegurando la unicidad del customerID.

✔️ Validación de coherencia lógica entre tiempo de contrato y cargos totales.

Tras estos pasos, el dataset quedó completo, consistente y listo para análisis.

🔹 Análisis Exploratorio de Datos (EDA) Distribución de la variable Churn

Se visualizó la proporción de clientes que permanecieron vs cancelaron mediante gráficos de barras y torta.

Se observó que el dataset presenta una proporción relevante de churn, lo que justifica el análisis y la necesidad de acciones de retención.

Análisis por variables categóricas

Se analizaron gráficos de barras cruzando Churn con variables clave:

Tipo de contrato:

Los clientes con contrato mes a mes presentan la mayor tasa de evasión.

Los contratos de 1 y 2 años muestran mayor estabilidad.

Método de pago:

Los pagos automáticos tienden a tener menor churn.

Servicios de soporte y seguridad:

La ausencia de soporte técnico y seguridad online está asociada a una mayor evasión.

Género:

No se observaron diferencias significativas en la evasión.

Análisis por variables numéricas

Mediante boxplots e histogramas se compararon clientes que cancelaron vs los que no:

Tiempo de contrato (tenure):

Clientes con menor antigüedad presentan mayor churn.

Gasto mensual:

Cargos mensuales más altos están asociados a mayor probabilidad de evasión.

Total gastado:

Clientes que no cancelan acumulan un mayor gasto total, reflejando mayor permanencia.

🔹 Conclusiones e Insights

A partir del análisis realizado, se destacan los siguientes hallazgos:

📌 La evasión se concentra principalmente en clientes nuevos.

📌 El contrato mes a mes es el mayor predictor de churn.

📌 Los cargos mensuales elevados incrementan el riesgo de cancelación.

📌 La falta de soporte técnico y seguridad online está fuertemente relacionada con la evasión.

📌 Variables demográficas como el género tienen un impacto mínimo.

Estos resultados muestran que el churn no ocurre al azar, sino que sigue patrones claros y accionables.

🔹 Recomendaciones Estratégicas

Con base en los insights obtenidos, se proponen las siguientes acciones:

Incentivar contratos de largo plazo

Ofrecer descuentos o beneficios por migrar de contratos mensuales a anuales.

Fortalecer la retención temprana

Programas de bienvenida y seguimiento para clientes con baja antigüedad.

Optimizar planes de alto costo

Revisar la percepción de valor en clientes con cargos mensuales elevados.

Promover servicios de soporte y seguridad

Incluir soporte técnico y seguridad online como paquetes promocionales.

Fomentar métodos de pago automáticos

Bonificaciones por afiliación a pagos electrónicos recurrentes.

🚀 Cierre

Este análisis proporciona una base sólida para la toma de decisiones estratégicas orientadas a reducir la evasión de clientes en Telecom X. Los resultados pueden ser utilizados tanto para acciones comerciales inmediatas como para el desarrollo de modelos predictivos de churn que permitan anticiparse a la pérdida de clientes.

