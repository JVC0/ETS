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
<h2>Mis Primeras Tablas</h2>

<table style="width:100%">
  <tr>
    <td rowspan="2"></td>
    <th colspan="2">1 Eval</th>
    <th colspan="2">2 Eval</th>
    <th colspan="2">3 Eval</th>
  </tr>
  <tr>
  <td style="background-color: Green">Aprobados</td>
  <td style="background-color: Red">Suspendidos</td>
  <td style="background-color: Green">Aprobados</td>
  <td style="background-color: Red">Suspendidos</td>
  <td style="background-color: Green">Aprobados</td>
  <td style="background-color: Red">Suspendidos</td>
  </tr>
  <tr>
    <th>Informatica</th>
    <td>20</td>
    <td>2</td>
    <td>19</td>
    <td>3</td>
    <td>22</td>
    <td>0</td>
  </tr>
  <tr>
    <th>Matematicas</th>
    <td>10</td>
    <td>12</td>
    <td>15</td>
    <td>7</td>
    <td>12</td>
    <td>10</td>
  </tr>

  <tr>
</tr>
 
</table>

</body>
</html>
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
    <th>Horas</th>
    <th>Lunes</th>
    <th>Martes</th>
    <th>Miercoles</th>
    <th>Jueves</th>
    <th>Viernes</th>
  </tr>
  <tr>
    <th>8:00-9:00</th>
    <td rowspan="2" style="background-color: RED">Matematicas</td>
    <td style="background-color: #A8422D">Lengua</td>
    <td>Musica</td>   
    <td></td>
    <td rowspan="2" style="background-color: RED">Matematicas</td>
  </tr>
  <tr>
    <th>9:00-10:00</th>
    <td>Ingles</td>
    <td>Ingles</td>
    <td style="background-color: pink">E Fisica</td>
  </tr>
  <tr>
    <th>10:00-10:30</th>
    <td colspan="5">Recreo</td>
  </tr>
  <tr>
    <th>10:30-11:30</th>
    <td style="background-color: pink">E Fisica</td>
    <td>Valenciano</td>
    <td rowspan="2" style="background-color: #A8422D">Lengua</td>
    <td style="background-color: Yellow">Informatica</td>
    <td>Ingles</td>
  </tr>
  <tr>
    <th>12:30-13:30</th>
    <td>Musica</td>
    <td style="background-color: pink">E Fisica</td>
    <td rowspan="2" style="background-color: RED">Matematicas</td>
    <td style="background-color: Yellow">Informatica</td>
    
  </tr>
  <tr>
    <th>13:30-14:30</th>
    <td></td>
    <td style="background-color: Yellow">Informatica</td>
    <td></td>
  </tr> 
</table>

</body>
</html>
```