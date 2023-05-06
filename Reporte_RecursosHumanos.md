<div align="center">
  <h1 align="center"> Reporte de Recursos Humanos </h1>
</div>

<h2> Objetivo </h2>
<p align='justify'>
  Analizar la gestión de recursos humanos de la empresa, a través del análisis y evaluación de los colaboradores, la implementación de un sistema de evaluación de desempeño y el establecimiento de una estructura de sueldos justa y competitiva.
</p>

<h2> Modelo de datos </h2>
<div style="text-align:center"><img src="https://user-images.githubusercontent.com/106001221/236578819-048cd9b4-2ed9-44e1-ab86-ab6899a3904d.png" /></div>

<h2> Análisis Dax </h2>

<h3> Sueldo promedio </h3>
Sueldo promedio = AVERAGE('Tabla Sueldo'[Sueldo])

<h3> Evaluación promedio </h3>
Evaluación promedio = (AVERAGE('Tabla Evaluacion'[Evaluación]))

<h3> Edad promedio </h3>
Edad Promedio = AVERAGE('Tabla Empleados'[Edad])

<h3> Total empleados </h3>
Total empleados = COUNTROWS('Tabla Empleados')

<h2>Dashboard</h2>
<div align="center">  <h3>Colaboradores</h3> </div>
<div align="center"><img src="https://user-images.githubusercontent.com/106001221/236590679-eeb6899d-8863-4cb9-8149-43bdf0411e0f.png" alt="Colaboradores"></div>

<div align="center">  <h3>Análisis de sueldo</h3> </div>
<div align="center"><img src="https://user-images.githubusercontent.com/106001221/236590716-ddf209bf-f122-47c6-b155-3ae7b1353499.png" alt="Análisis sueldo"></div>

<div align="center">  <h3>Evaluación de desempeño </div>
<div align="center"><img src="https://user-images.githubusercontent.com/106001221/236590961-0470b7f7-f36d-4855-8f33-0701dee0819d.png" alt="Evaluación desempeño"></div>
