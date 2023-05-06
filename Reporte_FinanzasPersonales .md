<div align="center">
  <h1 align="center"> Reporte de Finanzas Personales </h1>
</div>

<h2> Objetivo </h2>
<p align='justify'>
  En este proyecto se realiza un análisis de las finanzas de una persona anónima, evaluando detalladamente los ingresos, gastos, utilidad y saldo. Mediante este análisis, se busca proporcionar una visión clara de la situación financiera, identificar patrones de comportamiento y ofrecer recomendaciones para mejorar la gestión de los recursos económicos. 
  
  El objetivo es brindar a la persona una perspectiva más informada y estratégica sobre sus finanzas, permitiéndole tomar decisiones financieras más sólidas y alcanzar una mayor estabilidad y bienestar económico.
</p>

<h2> Modelo de datos </h2>

<div style="text-align: center;">
  <img src="https://user-images.githubusercontent.com/106001221/236595730-e88a23f9-0a90-45a4-9b21-081753082b21.png" alt="Modelo Datos">
</div>

<h2> Análisis Dax </h2>
<h3> Finanzas </h3>

- Gastos
```dax
Gastos = CALCULATE([Total Finanzas] , Finanzas[Tipo] = "gasTos")
```

- Ingresos
```dax
Ingresos = CALCULATE([Total Finanzas] , Finanzas[Tipo] = "ingresos")
```

- Saldo
```dax
Saldo = CALCULATE([Utilidad], FILTER(ALL(Finanzas),Finanzas[Fecha] <= MAX(Finanzas[Fecha])))
```

- Total
```dax
Total Finanzas = SUM(Finanzas[Cantidad])
```

- Utilidad
```dax
Utilidad = [Ingresos] - [Gastos]
```

<h3> Expectativas </h3>

- Meta
```dax
Meta = CALCULATE([Total Expectativas], Expectativas[Tipo]="Meta")
```

- Presupuesto
```dax
Presupuesto = CALCULATE([Total Expectativas], Expectativas[Tipo]="Presupuesto")
```

- Saldo esperadp
```dax
Saldo esperado = CALCULATE([Ut. esperada], FILTER(ALL(Expectativas),Expectativas[Fecha] <= MAX(Expectativas[Fecha])))
```

- Total Expectativas
```dax
Total Expectativas = SUM(Expectativas[Cantidad])
```

- Utilidad esperada
```dax
Ut. esperada = [Meta] - [Presupuesto]
```

<h3> Cuotas % </h3>

- Cuota de gastos
```dax
Cuota gastos = [Gastos]/[Presupuesto]
```

- Cuota de ingresos
```dax
Cuota Ingresos = [Ingresos]/[Meta]
```

- Cuota saldo
```dax
Cuota saldo = [Saldo]/[Saldo esperado]
```

- Cuota de utilidad
```dax
Cuota Utilidad = [Utilidad]/[Ut. esperada]
```

<h2>Dashboard</h2>

<div align="center">
  <img src="https://user-images.githubusercontent.com/106001221/236599640-2eb75818-41e6-486c-a3fa-0aa4515e9a3b.png">
  
  <h4> Medidas </h4>
  <img src="https://user-images.githubusercontent.com/106001221/236599701-ca01b754-77cb-49f7-84db-20c70cf7154d.png">
  
  <h4> Cuota de ingresos </h4>
  <img src="https://user-images.githubusercontent.com/106001221/236599847-900649c9-0c79-4513-84ea-8a6181f3b89b.png">
  
  <h4> Detalle de ingresos </h4>
  <img src="https://user-images.githubusercontent.com/106001221/236599902-112c7dfd-f554-4d12-9a69-fe394e36e335.png">
  
  <h4> Cuota de gastos </h4>
  <img src="https://user-images.githubusercontent.com/106001221/236599915-b0bd8364-9f92-44fc-a338-6fc26e48f542.png">

  <h4> Detalle de gastos </h4>
  <img src="https://user-images.githubusercontent.com/106001221/236599961-53871cea-d19c-49aa-a874-bc2b77c1d59f.png">

  <h4> Cuota de utilidad </h4>
  <img src="https://user-images.githubusercontent.com/106001221/236600052-ab1b399c-5614-4088-aeb0-c61760c91ab1.png">
  
  <h4> Detalle de utilidad </h4>
  <img src="https://user-images.githubusercontent.com/106001221/236600093-2a82edee-5884-4249-b997-a6311239811d.png">

  <h4> Cuota de saldo </h4>
  <img src="https://user-images.githubusercontent.com/106001221/236600127-01d0a3f3-c5d7-405b-8106-8038af9fd4b6.png">

</div>

