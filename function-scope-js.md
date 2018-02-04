## RETO: 
Identificar las funciones globales, locales, funciones de callback, expresions, statement, closure, scope, contextos de ejecucion, funciones que forman parte de la pila de ejecucion (stack execution) y funciones que forman parte de la cola de eventos (event queue).

## MODIFICACIÓN
Por convención, las variables y nombres de funciones deben estar declaradas en inglés y en algunos casos aquí no se cumplen:
function longitud(input) => function length(input);
function soloNumeros(input); => function justNumbers(input);
var sumaTotal => var totalSum;

## FUNCIONES GLOBALES: 
<pre>(document).ready(function(){});</pre>

## FUNCIONES LOCALES: 
<pre>
function activeButton();
function desactiveButton();
function length(input);
function justNumbers(input);
function isValidCreditCard(numberCard);
</pre>

## FUNCIONES DE CALLBACK:
<pre>
function justNumbers();
function isValidCreditCard();
</pre>


## FUNCTION EXPRESSIONS: 
* **El objeto función es creado cuando la declación se está ejecutando.**
<pre>
var creditCardNumber = justNumbers(length(numberCard));
</pre>

## FUNCTION STATEMENTS: 
* **El objeto función es creado antes de que la declaración es ejecutada y después de que la declaración es invocada, es decir, pueden ser invocadas en cualquier parte del documento. No se recomienda su uso por lo mismo.**
<pre>
function activeButton();
function desactiveButton();
function length();
function justNumbers();
function isValidCreditCard();
</pre>

## IIFE’s/ Immediately Invoked Function Expressions: 
* **O funciones autoinvocables son funciones Expressions que no son puestas inmediatamente en memoria, sino que son puestas una vez que se corran.**
No usadas.

## CLOSURE: 
* **Todo tipo de variable que se declare dentro de un ambito de la función externa y es utilizada por la función anidada pertenecerá al closure.Es decir que una función definida dentro del closure “recuerda” el entorno en el que se ha creado y tiene acceso a las variables de ese entorno (scope).**
<pre>
function isValidCreditCard(numberCard); 
function justNumbers(input);
</pre>

## STACK EJECUTION: 
* **Contexto de ejecución apilados. El que permanece arriba de la pila es la función que se está ejecutando actualmente. Un nuevo contexto de ejecución es creado y puesto arriba de la pila cuando una función es invocada, y retirada de la fila cuando la función finaliza.**
<pre>
isValidCreditCard();
activeButton()
function desactiveButton()
function length(input)
function justNumbers(input)
function isValidCreditCard(numberCard) 
</pre>

## EVENT QUEUE: 
* **Cada vez que se llama a un evento o se hace una operación asincrónica, es añadida a la *tabla de eventos(event table)*. Cuando la pila tiene suficiente capacidad, un mensaje es tomado del queue (cola) y  se procesa, el cual consiste en llamar a la función asociada. Este mensaje termina de procesarse cuando *la pila se vuelve vacia de nuevo*. Ejemplo: Si un usuario da click a un botón y no se proporciona nunfuna función callback, entonces ningun mensaje estaria en cola.**
<pre>
$inputCard.on('input', function(){})
</pre>
