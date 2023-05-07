<div align="center">
  <h1 align="center"> Reporte de Tickets
</div>
    
<h2> Objetivo </h2>
<p align='justify'>
 Analizar y evaluar el desempeño de los agentes de soporte en la resolución de tickets. Con este análisis, se busca medir la cantidad de tickets resueltos y el timepo realizado por cada agente. Se busca identificar los agentes más destacados, aquellos que han logrado resolver un mayor número de tickets en un tiempo óptimo y con una alta satisfacción del cliente. Además, se busca identificar oportunidades de mejora y brindar retroalimentación a los agentes para optimizar su desempeño y garantizar una atención de calidad a los usuarios.
</p>

<h2> Modelo de datos </h2>

<div align="center">
<img src="https://user-images.githubusercontent.com/106001221/236701042-cb0c043e-a422-4fa9-ae51-b77244f23574.png">
</div>

<h2> Medidas Dax </h2>
    
- Total de tickets
```dax
Total Tickets = IF( ISBLANK (COUNTROWS(F_Tickets) ) , 0 , COUNTROWS(F_Tickets) )
```
    
- Total de tickets positivos
```dax
Total Tickets Positivos = CALCULATE([Total Tickets] , 'Dim_Satisfacción'[Status] = "Positivo")
```
    
- Total de tickets de problemas
```dax
Total Tickets Problema = CALCULATE([Total Tickets] , F_Tickets[Tipo] = "Problema")
```

- Total de tickets no blanck
```dax
Total Tockets NoBlanck = COUNTROWS(F_Tickets)
```
  
- Porcentaje de tickets positivos
```dax
% Positivo = DIVIDE([Total Tickets Positivos] , [Total Tickets] , 0)
```

- Porcentaje de tickets de problemas
```dax
% Problemas = DIVIDE([Total Tickets Problema] , [Total Tickets] , 0)
```

- Promedio de días que permanecio abierto el ticket
```dax
Promedio Días Abierto = AVERAGE(F_Tickets[Días Resolución])
```

- Promedio de tickets satisfechos
```dax
Promedio Satisfacción = AVERAGE(F_Tickets[Satisfacción])
```

- Ranking de días 
```dax
Rank Días = RANKX(ALL(D_Agentes) , [Promedio Días Abierto] , , ASC )
```

- Ranking de satisfacción de tickets
```dax
Rank Satisfacción = RANKX(ALL(D_Agentes) , [Promedio Satisfacción])
```
    
- Ranking de tickets resueltos 
```dax
Rank Tickets = RANKX( ALL(D_Agentes) , [Total Tickets])
```
    
- Ranking total de días
```dax
Rank Final = RANKX(ALL(D_Agentes) , [Rank Total] , , ASC)
```

- Rank total de tickets resueltos 
```dax
Rank Tickets Allselected = RANKX( ALLSELECTED(D_Agentes) , [Total Tickets])
```

- Ranking total 
```dax
Rank Total = [Rank Tickets] + [Rank Días] + [Rank Satisfacción] 
```

- Tickets por agente
```dax
Tickets por agente = ROUND(DIVIDE([Total Tickets] , [Total Agentes] , 0) , 0 )
```
    
- Total de agentes all selected
```dax
Total por agente allselected = CALCULATE([Tickets por agente] , ALLSELECTED(F_Tickets))
```
    
- Tickets por agente variación 
```dax
Tickets por agente variación = [Total Tickets] - [Total por agente allselected]
```

- Tickets por agente variable grupo
```dax
Tickets por agente var grupo = IF([Tickets por agente variación] >= 0 , "Arriba del promedio" , "Debajo del promedio")
```

- Total de todos los tickets 
```dax
Total tickets all = CALCULATE([Total Tickets] , ALL(F_Tickets))
```
    
- Total de tickets all selected
```dax
Total tickets allselected = CALCULATE([Total Tickets] , ALLSELECTED(F_Tickets))
```
    
<h2>Dashboard</h2>
<div align="center">
  
  ![Principal](https://user-images.githubusercontent.com/106001221/236701771-002c46d8-e1e7-4043-8700-449797acb8eb.png)
  
  <h3> Balance general </h3>
  
  ![Balance general](https://user-images.githubusercontent.com/106001221/236701914-b8459135-9de3-4c17-a7ab-2782e44c7c4f.png)
  
  <h3> Ranking </h3>
  
  ![Ranking](https://user-images.githubusercontent.com/106001221/236702000-23e6cca5-ab49-4b7c-ab70-21c07d85dbab.png)

  ![Ranking con informe complemetario](https://user-images.githubusercontent.com/106001221/236702009-1052fc21-feb0-47d4-af96-ddecf0f369d8.png)

  <h3> Ranking general </h3>
  
  ![Ranking general](https://user-images.githubusercontent.com/106001221/236702070-0215a9d2-5e1c-4233-81c1-73a157de3b56.png)

  <h3> Ranking de agentes </h3>
  
  ![Ranking de agentes](https://user-images.githubusercontent.com/106001221/236702128-7e21768c-eee4-48ea-a8b3-8c12b43cc0f4.png)



 </div>
