# <p align="center"> Ventas en tiendas Appol </p>

## Objetivo
<p alig='justufy'>
A través de este informe, se busca analizar el desempeño de las ventas de la empresa durante el año 2017 al 2019, 
desglosando por continentes, márgenes, año y trimestre, para así proporcionar recomendaciones para mejorar el 
rendimiento de la empresa en cada uno de ellos. 
</p>

## Modelo de datos
![Modelo de datos](https://user-images.githubusercontent.com/106001221/236519514-03f6b706-d8be-46ed-9ef8-818e8030d819.png)

## Análisis de ventas
#### Total ingresos
TotalIngresos = SUM('Tabla Datos'[Ingresos])
#### Total Gastos
TotalGastos = SUM('Tabla Datos'[Gastos])
#### Utilidad
Utilidad = [TotalIngresos] - [TotalGastos]
#### Margen
Margen = DIVIDE([Utilidad] , [TotalIngresos] , 0)

## Dashboard
![Dashboard](https://user-images.githubusercontent.com/106001221/236519648-82d92a6a-0d3f-4bad-8751-5bca3f997a7f.png)

## Conclusiones

<p align="justify">
La empresa ha obtenido una utilidad de 671.11 millones con un margen del 19.95%, lo que indica que la rentabilidad es aceptable. Las ventas más altas se registraron en los continentes de América, Asia y Europa, lo que puede sugerir oportunidades de expansión en estas regiones. Australia es el país con el margen más alto, mientras que Estados Unidos es el país que ha generado la mayor utilidad para la empresa.
</p>

## Referencias
"Curso de Power BI Desktop", impartido por "Javier Gómez" en "Udemy".
