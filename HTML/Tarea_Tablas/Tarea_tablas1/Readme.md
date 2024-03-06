# Ejercicio Practico
### Tabla resultante del codigo
<!DOCTYPE html>
<html>
<style>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
</style>
<body>

<table style="width:100%">
  <tr>
    <td></td>
    <th colspan="3"><img src="120_ipod.png" height="150px"></th>
    <th colspan="2"><img src="100_ipod.png" height="150px"></th>
  </tr>
  <tr>
    <th>Capacidad</th>
    <td>2GB</td>
    <td>4GB</td>
    <td>8GB</td>
    <td>32GB</td>
    <td>2GB</td>
  </tr>
  <tr>
    <th>Colores</th>
    <th>Blanco</th>
    <td><ul><li>Negro</li><li>Rosado</li><li>Dorado</li></ul></td>
    <th>Negro</th>
    <td colspan="2" ><ul><li>Negro</li><li>Blanco</li></ul></td>
  </tr>
  <tr>
    <th>Pantalla</th>
    <th colspan="3">3 pulgadas</th>
    <th colspan="3">7 pulgadas</th>
  </tr>
  <tr>
    <th rowspan="3">Tiempo de Carga</th>
    <th colspan="3" rowspan="3">1 hora</th>
    <th colspan="3" rowspan="1.5">5 horas</th>
    <tr>
  <th colspan="3" rowspan="1.5">30 minutos</th>
  
</table>

</body>
</html>

# Codigo de tabla

```html
<!DOCTYPE html>
<html>
<style>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
</style>
<body>

<table style="width:100%">
  <tr>
    <td></td>
    <th colspan="3"><img src="120_ipod.png" height="150px"></th>
    <th colspan="2"><img src="100_ipod.png" height="150px"></th>
  </tr>
  <tr>
    <th>Capacidad</th>
    <td>2GB</td>
    <td>4GB</td>
    <td>8GB</td>
    <td>32GB</td>
    <td>2GB</td>
  </tr>
  <tr>
    <th>Colores</th>
    <th>Blanco</th>
    <td><ul><li>Negro</li><li>Rosado</li><li>Dorado</li></ul></td>
    <th>Negro</th>
    <td colspan="2" ><ul><li>Negro</li><li>Blanco</li></ul></td>
  </tr>
  <tr>
    <th>Pantalla</th>
    <th colspan="3">3 pulgadas</th>
    <th colspan="3">7 pulgadas</th>
  </tr>
  <tr>
    <th rowspan="3">Tiempo de Carga</th>
    <th colspan="3" rowspan="3">1 hora</th>
    <th colspan="3" rowspan="1.5">5 horas</th>
    <tr>
  <th colspan="3" rowspan="1.5">30 minutos</th>
  
</table>

</body>
</html>
```
