# Estudio y optimización del cuerpo de bomberos de la comunidad de Madrid

## Descripción del proyecto

En este repositorio se realizará un proyecto para la asignatura de $\textit{Descubrimiento de Conocimiento en Datos}$ $\textit{Complejos}$, del grado de $\textbf{Ciencia de Datos e Inteligencia Artificial}$ de la Universidad Politécnica de Madrid. El objetivo principal es conseguir predecir el número aproximado de intervenciones del cuerpo de bomberos de la comunidad de Madrid, de forma que se pueda optimizar según las necesidades.

Para ello, se emplearán los datos de avisos a los bomberos proporcionados por el _Portal de datos abiertos del Ayuntamiento de Madrid_. Además, se emplearán los datos obtenidos por el cuerpo de Policía y el SAMUR para buscar correlación entre las alertas por la consideración de posibles casos de variables exógenas.

## Obtención de Datos

Los datos que se han extraido son:

- Actuaciones del Cuerpo de Bomberos: https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=fa677996afc6f510VgnVCM1000001d4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default
- Policía Municipal. Datos estad ́ısticos actuaciones Policía Municipal: https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/vgnextoid=bffff1d2a9fdb410VgnVCM2000000c205a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default
- Activaciones del SAMUR-Protección Civil: https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=50d7d35982d6f510VgnVCM1000001d4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default

Se han extraido los datasets por año, exceptuando las intervenciones del cuerpo de policía que se encuentran por meses. Para poder trabajar con los datos adecuadamente se ha realizado la limpieza y preprocesamientos pertinentes, estos se pueden encontrar en la carpeta "**limpieza de datos**". Todos los datos se encuentran en la carpeta "**Data**".

## Limpieza de datos

En esta carpeta hay 2 notebooks:

- "_CargaSamurBomberos.ipynb_": Incorpora todos los datos en un mismo dataframe en un intervalo desde 2017-2023.
- "_limpieza_datos_policia.ipynb_": Al tener los datos separados en meses en vez de años, se ha dividido el preprocesamiento de las incidencias del cuerpo de policía en un notebook separado. El resultado final es el mismo, obtener una versión estandarizada con un solo dataframe de las intervenciones entre el periodo 2017-2023.

No es necesaria la ejecución de estos notebooks, los dataframes resultantes se pueden encontrar en la carpeta **Data** como los archivos _(bomberos_completo.csv)_, _(actuaciones_policia_total.csv)_, _(samur_completo.zip)_.

## Análisis de los tres cuerpos

En la carpeta **analisis** se encuentra el notebook "_analisis_cuerpos.ipynb_", que contiene todos los análisis realizados a las intervenciones de los tres cuerpos, junto con las predicciones con modelos de análisis de series temporales, vease ARMA, ARIMA, SARIMAX, LSTM y técnicas de suavizado (Holt-Winters). Todas las explicaciones de los resultados obtenidos se pueden encontrar en el documento "_Informe_del_analisis.pdf_", en el que se realiza un estudio detallado de los procedimientos que se han realizado, además de la justificación de estos con las investigaciones, comparativas y referencias empleadas.


$\begin{table}[ht]
\caption{Comparativa de resultados (error)}\label{comparativa_errores}
\renewcommand\arraystretch{1.5}
\noindent\[
\begin{array}{|c|c|c|c|}
\hline
Modelo&MAE&MSE&RMSE\\
\hline 
SARIMAX(policía\_exógena)&365.39&282607.48&531.61\\
\hline 
SARIMAX(Samur\_exógena)&318.86&153313.32&391.55\\
\hline
ARIMA&361.20&220006.98&469.05\\
\hline
MA&398.99&219592.39&468.61\\
\hline
SARIMAX(Samur\_y\_policía\_exógenas)&494.80&426328.59&652.94\\
\hline
\end{array}
\]
\end{table}$
