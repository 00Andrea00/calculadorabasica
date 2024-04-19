# Calculadora básica
- Versión: 0.1
- Autor: **Andrea**
- Licencia: MIT

![Captación de la app](calculadora.png)

## Descripción general
Aplicación web diseñada para realizar operaciones matemáticas básicas.

## Instalación
Descargar el zip haciendo click en el enlace
[Calculadora básica](https://github.com/00Andrea00/calculadorabasica.git)
o en el Shell utilizar el comando git clone:
```shell
git clone https://github.com/00Andrea00/calculadorabasica.git
```
Una vez descargado deberá incluirse en un repositorio de GitHub y ejecutarlo a través de un navegador web.
```
http://localhost:3000/calculadorabasica
```

## Tecnologías utilizadas
**HTML, Javascript y CSS**

![Icono-HTML](img/filetype-html.svg)
![Icono-Javascript](img/filetype-js.svg)
![Icono-CSS](img/filetype-css.svg)

## Instrucciones de uso
1. Rellena los campos de la operación escribiendo o buscando con las flechas los números con los que se quiere operar.
2. Selecciona la operación que quieres realizar en el desplegable.
3. Pulsa el botón calcular (el resultado aparecerá debajo subrayado en negro)

## Solución de problemas
- Los campos no permiten la entrada de texto alfanumérico.
- Si se equivoca de operación podrá volver a seleccionarla de manera instantánea.
- Habrá actualizaciones futuras para mejora e implementación del sistema.

## Objetivos
Ayudar a los usuarios a realizar operaciones matemáticas simples de una manera rápida y sencilla.

## Arquitectura del proyecto
- HTML(definición de la estructura de la web):
```html
<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aplicación web simple</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div class="container">
        <h1>Calculadora básica</h1>
        <div class="borde">

     
        <div>
            <input type="number" id="num1" placeholder="Primer número">
        </div>
        <div>
            <input type="number" id="num2" placeholder="Segundo número">
        </div>
        <div>
            <select id="operacion">
                <option value="+">Suma</option>
                <option value="-">Resta</option>
                <option value="*">Multiplicación</option>
                <option value="/">División</option>
            </select>
        </div>
        <div>
            <button onclick="calcular()">Calcular</button>
        </div>
        <p id="resultado">
            
        </p>
    </div>
    </div>
    <script src="script.js"></script>
</body>

</html>
```
- Javascript (definición de las funcionalidades de la web):
```javascript
const divResultado = document.getElementById('resultado')
function calcular() {
    const num1 = parseFloat(document.getElementById('num1').value);
    const num2 = parseFloat(document.getElementById('num2').value);
    if (isNaN(num1) || isNaN(num2)) {
        divResultado.textContent= 'En ambos campos se deben introducir números';
        return;
    }
    const operacion = document.getElementById('operacion').value;

    let resultado;

    switch (operacion) {
        case '+':
            resultado = num1 + num2;
            break;
        case '-':
            resultado = num1 - num2;
            break;
        case '*':
            resultado = num1 * num2;
            break;
        case '/':
            if (num2 === 0) {
                divResultado.textContent= 'No se puede dividir por cero';
                return;
            }
            resultado = num1 / num2;
            break;
        default:
            divResultado.textContent= 'Operación no válida';
            return;
    }

   divResultado.textContent = `
    El resultado de la operación ${operacion} es: ${resultado}
    `;
}
```
- CSS (definición del diseño de la web):
```css
body {
    font-family: sans-serif;
}

.container {
    max-width: 600px;
    margin: auto;
    text-align: center;
}

h1 {
    text-align: center;
    margin-bottom: 20px;
}

input[type="number"],
select {
    width: 100px;
    margin-bottom: 10px;
}

button {
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    border: none;
    cursor: pointer;
}

#resultado {
    text-align: center;
    font-family: consola, monospace;
    color: greenyellow;
    background-color: black;
    font-weight: bold;
    margin-top: 20px;
}
```

## Funcionalidades
|Generales|Específicas|
|--|--|
|Agilizar el tiempo de trabajo empleado en el cálculo de variables|Realizar sumas, restas, multiplicaciones y divisiones más rápido|