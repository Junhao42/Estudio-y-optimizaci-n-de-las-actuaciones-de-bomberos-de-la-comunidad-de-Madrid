# Estudio y optimización del cuerpo de bomberos de la comunidad de Madrid

## Descripción del proyecto

En este repositorio se realizará un proyecto para la asignatura de $\textit{Descubrimiento de Conocimiento en Datos}$ $\textit{Complejos}$, del grado de $\textbf{Ciencia de Datos e Inteligencia Artificial}$ de la Universidad Politécnica de Madrid. El objetivo principal es conseguir predecir el número aproximado de intervenciones del cuerpo de bomberos de la comunidad de Madrid, de forma que se pueda optimizar según las necesidades.

Para ello, se emplearán los datos de avisos a los bomberos proporcionados por el _Portal de datos abiertos del Ayuntamiento de Madrid_. Además, se emplearán los datos obtenidos por el cuerpo de Policía y el SAMUR para buscar correlación entre las alertas por la consideración de posibles casos de variables exógenas.

# Obtención de Datos

Los datos que se han extraido son:

- Actuaciones del Cuerpo de Bomberos: https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=fa677996afc6f510VgnVCM1000001d4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default
- Policía Municipal. Datos estad ́ısticos actuaciones Policía Municipal: https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/vgnextoid=bffff1d2a9fdb410VgnVCM2000000c205a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default
- Activaciones del SAMUR-Protección Civil: https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=50d7d35982d6f510VgnVCM1000001d4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default

Se han extraido los datasets por año, exceptuando las intervenciones del cuerpo de policía que se encuentran por meses. Para poder trabajar con los datos adecuadamente se han realizado la limpieza y preprocesamientos pertinentes, estos se encuentran en la carpeta **limpieza**
