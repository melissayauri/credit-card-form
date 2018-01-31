# SCOPE-JS

## OBJETIVO
identificar las funciones globales, locales, funciones de callback, expresions, statement, clousure, scope, contextos de ejecucion,stack execution, event queue del código javascript.

* **Funciones globales** : Forman parte del propio núcleo de JavaScript.Ejemplo:

 - **(Linea 1)**
 ```javascript
 $(document).ready(function() {});
 };
   ```

* **Variables globales** : Se puede acceder dentro como fuera de la función.Ejemplo:

 - **(Linea 6)**
 ```javascript
  var $inputCard = $('#card-number');
   ```

 - **(Linea 7)**
 ```javascript
   var $inputMonth = $('.input-month');
   ```

 - **(Linea 8)**
 ```javascript
   var $inputYear = $('.input-year');
   ```

 - **(Linea 9)**
 ```javascript
   var $buttonNext = $('#next');
   ```

 - **(Linea 10)**
 ```javascript
   var regexOnlyNumbers = /^[0-9]+$/;
   ```

 - **(Linea 11)**
 ```javascript
 var labelErrorOrSuccessMessages =$('label[for="card-number"]');
   ```




* **Funciones locales** : Aquellas que se encuentran dentro de otra función. Ejemplo:

 - **(Linea 19)**
 ```javascript
  function activeButton() {};
};
   ```
 - **(Linea 24)**
 ```javascript
  function desactiveButton() {};
};
```
 - **(Linea 29)**
 ```javascript
  function longitud(input) {};
};
```

 - **(Linea 36)**
 ```javascript
   function soloNumeros(input) {};
};
```

 - **(Linea 44)**
 ```javascript
    function isValidCreditCard(numberCard) {};
};
```

* **Funciones callback** : Sucede cuando una funcion acepta como parámetro otra función la cual se ejecutará al finalizar una tarea

 - **(Linea 44-45)**
 ```javascript
 function isValidCreditCard(numberCard) {
   var creditCardNumber = soloNumeros(longitud(numberCard));
};
   ```

 - **(Linea 29-33)**  
```javascript
  function longitud(input) {
     if (input.trim().length === 16) {
       return input;
     }
   }
  ```

  - **(Linea 36-41)**  
 ```javascript
 function soloNumeros(input) {
  var regex = /^[0-9]+$/;
  if (regex.test(input)) {
    return input;
  }
}
   ```
* **Expresiones** : Patrones utilizados para encontrar una determinada combinación de caracteres. Ejemplo :

 - **(Linea 37)**
 ```javascript
  var regex = /^[0-9]+$/ , encuentra cualquier caracter que no sea un digíto.
};
   ```

* **Staments** : Son instrucciones que se ejecutan en el navegador. Ejemplos :

 -  **(Linea 67)**
 ```javascript
  console.log('Verifique el numero de su tarjeta');
};
   ```

 -  **(Linea 71)**
 ```javascript
   console.log('Verifique el numero de su tarjeta');
};
   ```


* **Clousure** : Funciones que manejan variables independientes

* **Contexto de ejecución** : Entorno en el que se evalua el código actual.

 - **(Linea 15)**
 ```javascript
  isValidCreditCard($(this).val().trim());
};
   ```

 - **(Linea 20)**
 ```javascript
    $buttonNext.attr('disabled', false);
};
   ```

 - **(Linea 25)**
 ```javascript
     $buttonNext.attr('disabled', true);
};
   ```

 - **(Linea 30-31)**
 ```javascript
 if (input.trim().length === 16) {
     return input;
   }
};
   ```

 - **(Linea 37-40)**
 ```javascript
 var regex = /^[0-9]+$/;
    if (regex.test(input)) {
      return input;
    }
   ```

  - **(Linea 45-73)**  
  ```javascript
  var creditCardNumber = soloNumeros(longitud(numberCard));
      if (creditCardNumber !== undefined) {
        var arr = [];
        var sumaTotal = 0;
        for (var index = creditCardNumber.length - 1; index >= 0; index--) {
          arr.push(creditCardNumber[index]);
        }
        for (var index = 1; index < arr.length; index = index + 2) {
          arr[index] = arr[index] * 2;
          if (arr[index] >= 10) {
            arr[index] = arr[index] - 9;
          }    
        }

        for (var index = 0; index < arr.length; index++) {
          sumaTotal = sumaTotal + parseInt(arr[index]);
        }

        if (sumaTotal % 10 === 0) {
          console.log('Es una tarjeta valida');
          activeButton();
        } else {
          console.log('No es un numero valido');
          desactiveButton();
        }
      } else {
        console.log('Verifique el numero de su tarjeta');
        desactiveButton();  
      }
      ```


*  **Cola de eventos()** : Es un mecanismo que permite manejar los eventos para un determinado elemento.

 -  **(Linea 14)**

 ```javascript
  $inputCard.on('input', function() {});
   ```


##  Referencias

 * [Funciones globales y locales](https://www.w3schools.com/js/js_scope.asp)

 * [Stamenents](https://www.youtube.com/watch?v=lTsTTAaR8bs)

 * [Expresiones](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_Expressions)

 * [Cola de eventos](http://casivaagustin.com.ar/index.php/javascript-enlace-de-eventos/)

 * [Contexto de ejecución](http://casivaagustin.com.ar/index.php/javascript-enlace-de-eventos/)

* [Pila de ejecución](https://hackernoon.com/execution-context-in-javascript-319dd72e8e2c)
