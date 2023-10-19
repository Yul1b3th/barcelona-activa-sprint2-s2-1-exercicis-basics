# S2.1. Exercicis Bàsics

* [1.1: Arrow functions](#bloc-11-arrow-functions 'Anar')
  * Conversió de funcions
  * Funció de fletxa sense paràmetres
  * Ús de 'this' en les funcions de fletxa
  * Funció de fletxa dins d'un loop
  * Funció de fletxa amb 'setTimeout'

* [1.2: Operador ternari](#bloc-12-operador-ternari 'Anar')
  * Operador ternari bàsic
  * Ús amb operadors de comparació
  * Ús enllaçat d'operadors ternaris
  * Operador ternari amb funcions
  * Operador ternari dins un bucle

* [1.3: Callbacks](#bloc-13-callbacks 'Anar')
  * Callback bàsic
  * Callbacks amb operacions matemàtiques
  * Ús de callbacks en funcions asíncrones
  * Callbacks amb arrays
  * Escriu una funció processarCadena que accepti dos paràmetres

* [1.4: Rest & Spread operators](#bloc-14-rest--spread-operators 'Ir')
  * Operador Spread en Arrays
  * Operador Rest en Funcions
  * Copiant objectes amb Spread
  * Rest en Destructuring
  * Spread en Funcions
  * Fusionant Objectes amb Spread

* [1.5: Array transformations](#bloc-15-array-transformations 'Anar')
  * Map
  * Filter
  * Find
  * Reduce
  * Combinar mètodes
  * Every / Some

* [1.6: Array loops](#bloc-16-array-loops 'Anar')
  * forEach
  * for-of
  * filter
  * for-in
  * for-of amb index

* [1.7: Promises & Async/Await](#bloc-17-promises--async--await 'Anar')
  * Creació d'una Promesa
  * Utilització d'una Promesa
  * Promesa amb reject
  * Ús de async/await
  * Gestió d'errors amb async/await
  * Promise.all

---

## Bloc 1.1: Arrow functions

### ![nivel 1](img/estrella1.svg) Nivell 1

#### Exercici 1

**Conversió de funcions:** Tens una funció add que accepta dos paràmetres i retorna la seva suma. Converteix-la en una funció de fletxa. Per exemple: function add(a, b) {return a + b;}.

```js
const add = (a, b) => a + b;
```

#### Exercici 2

**Funció de fletxa sense paràmetres:** Crea una funció de fletxa anomenada randomNumber que no necessiti paràmetres i que retorni un número aleatori entre 0 i 100.

```js
const randomNumber = () => Math.floor(Math.random() * 101);
```

#### Exercici 3

**Ús de 'this' en les funcions de fletxa:** Crea una classe person que tingui una propietat name i una funció greet que utilitzi una funció de fletxa. La funció ha d'imprimir una salutació que inclogui el nom de la persona. Per exemple: console.log(Hola, ${this.name});.

```js
class Person {
  name = '';
  constructor(name) {
    if (!name) throw Error('Necesitamos el nombre');
    this.name = name;
  }
  greet = () => console.log(`Hola, ${this.name}`);
}

const yuli = new Person('yuli');
yuli.greet();
```

### ![nivel 2](img/estrella2.svg) Nivell 2

#### Exercici 4

**Funció de fletxa dins d'un loop:** Crea una funció anomenada printNumbers que accepti un array de números i utilitzi un loop for per imprimir cada número a la consola utilitzant una funció de fletxa.

```js
const printNumbers = ((numbers) => {
  for (let number of numbers) {
    console.log(number);
  }
})([1, 2, 3, 4]);
```

### ![nivel 3](img/estrella3.svg) Nivell 3

#### Exercici 5

**Funció de fletxa amb 'setTimeout':** Crea una funció de fletxa que imprimeixi un missatge a la consola després d'esperar 3 segons.

```js
setTimeout(() => {
  console.log('¡Hola!');
}, 3000);
```


<br>

[![Anar a Inici](img/arrow-up-in-a-circle.png)](#s21-exercicis-bàsics 'Anar a Inici')

<br>

---

## Bloc 1.2: Operador ternari

### ![nivel 1](img/estrella1.svg) Nivel 1

#### Exercici 1

**Operador ternari bàsic:** Escriu una funció potConduir que accepti l'edat com a paràmetre i utilitzi l'operador ternari per determinar si l'usuari pot conduir. Si l'edat és 18 o més, ha de retornar 'Pots conduir'.Si no, ha de retornar 'No pots conduir'.

```js
const potConduir = ((edat) => {
  (edat >= 18) 
    ? console.log('Pots conduir') 
    : console.log('No pots conduir');
})(17);
```

#### Exercici 2

**Ús amb operadors de comparació:** Escriu una expressió que utilitzi l'operador ternari per determinar quin dels dos nombres donats (num1 i num2) és més gran. Si num1 és més gran, retorna 'num1 és més gran'. Si no, retorna 'num2 és més gran'.

```js
(num1 > num2) 
  ? console.log('num1 és més gran') 
  : console.log('num2 és més gran');
```

### ![nivel 2](img/estrella2.svg) Nivel 2

#### Exercici 3

**Ús enllaçat d'operadors ternaris:** Escriu una expressió que utilitzi enllaços d'operadors ternaris per determinar si un número és positiu, negatiu o zero.

```js
const resultado = 
(num > 0) 
  ? 'es positivo' 
  : (num < 0) 
  ? 'es negativo' 
  : 'es cero';
```

**Operador ternari amb funcions:** Crea una funció trobarMaxim que accepti tres paràmetres( a, b, c ) i utilitzi l'operador ternari per determinar el valor màxim.

```js
const trobarMaxim = (a, b, c) => {
  console.log({ a, b, c });
  const resultado =
    (a > b && a > c)
      ? `a es el valor maximo ${a}`
      : (a > b && b > c)
      ? `b es el valor maximo ${b}`
      : `c es el valor maximo ${c}`;
  console.log(resultado);
};

trobarMaxim(7, 5, 9);
```

### ![Nivell 3](img/estrella3.svg) Nivell 3

#### Exercici 4

**Operador ternari dins un bucle:** Escriu una funció parOImpar que accepti un array de números i utilitzi un bucle per a recórrer l'array. Dins del bucle, utilitza l'operador ternari per a determinar si cada número és parell o imparell.

```js
const arr = [13, 5, 24, 47, 18, 36];

const parOImpar = ( arr ) => {
 let i = 0;
 while ( arr[i] ) {
  let mensaje = ( arr[i] % 2 === 0 ) ? 'par' : 'impar';
  console.log( `El numero ${arr[i]} es ${mensaje}` );
  i++;
 };
}

parOImpar( arr );
```

<br>

[![Anar a Inici](img/arrow-up-in-a-circle.png)](#s21-exercicis-bàsics 'Anar a Inici')

<br>

---

## Bloc 1.3: Callbacks

### ![Nivell 1](img/estrella1.svg) Nivell 1

#### Exercici 1
**Callback bàsic:** Escriu una funció anomenada processar que accepti dos paràmetres: un nombre i una funció de callback.La funció processar ha d'invocar la funció de callback, passant el nombre com a paràmetre.

```js
function processar( nom, callback ) {
 callback( nom );
};

processar( 'Yuli', ( nom ) => { console.log( nom ); } );
```

#### Exercici 2
**Callbacks amb operacions matemàtiques:** Escriu una funció calculadora que accepti tres paràmetres: dos nombres i una funció de callback.La funció calculadora ha d'invocar la funció de callback amb els dos nombres com a paràmetres. Després, crida calculadora amb una funció que faci la suma dels dos nombres.

```js
function calculadora( num1, num2, callback ) {
 callback( num1, num2 )
};

calculadora( 2, 3, ( num1, num2 ) => {
 let suma = num1 + num2;
 console.log( suma );
} );
```

### ![Nivell 2](img/estrella2.svg) Nivell 2

#### Exercici 3

**Ús de callbacks en funcions asíncrones:** Escriu una funció esperarISaludar que accepti dos paràmetres: un nom i una funció de callback.La funció ha d'esperar 2 segons i llavors invocar la funció de callback, passant el nom com a paràmetre.

```js
function esperarISaludar( nom, callbak ) {
 setTimeout( () => { callbak( nom ) }, 2000 );
};
esperarISaludar( 'Yuli', ( nom ) => { console.log( nom ); } );
```

#### Exercici 4
**Callbacks amb arrays:** Escriu una funció processarElements que accepti dos paràmetres: un array i una funció de callback.La funció processarElements ha d'invocar la funció de callback per cada element de l'array.

```js
function processarElements( arr, callback ) {
 for ( let elemento of arr ) {
  callback( elemento );
 }
}

processarElements( ['a', 'b', 'c'], ( elemento ) => {
 console.log( elemento );
} );
```

### ![Nivell 3](img/estrella3.svg) Nivell 3

#### Exercici 5

Escriu una funció processarCadena que accepti dos paràmetres: una cadena de caràcters i una funció de callback.La funció processarCadena ha de convertir la cadena a majúscules i llavors invocar la funció de callback amb la cadena transformada.

```js
function processarCadena( cadena, callback ) {
 let nuevaCadena = cadena.toUpperCase();
 callback( nuevaCadena );
};

processarCadena( 'hola', ( recibirCadena ) => { console.log( recibirCadena ); } );
```

<br>

[![Anar a Inici](img/arrow-up-in-a-circle.png)](#s21-exercicis-bàsics 'Anar a Inici')

<br>

---

## Bloc 1.4: Rest & Spread operators

### ![Nivell 1](img/estrella1.svg) Nivell 1

### Exercici 1
**Operador Spread en Arrays:** Crea dues arrays, array1 i array2. Utilitza l'operador spread per a crear una tercera array que contingui tots els elements de array1 i array2.##

```js
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [...arr1, ...arr2];
console.log( arr3 );
```

### Exercici 2

**Operador Rest en Funcions:** Crea una funció 'suma' que utilitzi l'operador rest per a acceptar un nombre indeterminat d'arguments i retornar la seva suma.

```js
const suma = ( ...numeros ) => numeros.reduce( ( resultado, num ) => resultado + num, 0 );

suma( 1, 2, 8 );
```

### ![Nivell 2](img/estrella2.svg) Nivell 2

#### Exercici 3

**Copiant objectes amb Spread:** Crea un objecte 'objecte1'. Després crea un segon objecte, 'objecte2', que sigui una còpia de 'objecte1' utilitzant l'operador spread. Canvia una propietat de 'objecte2' i comprova que 'objecte1' no ha canviat.

```js
const objecte1 = {
 nom: 'Ana',
 sexo: 'Femenino',
 estadoCivil: 'Soltera'
};

const objecte2 = { ...objecte1 };
console.log( objecte1 );
objecte2.nom = 'Luis';
objecte2.edad = 32;
console.log( objecte2 );
```

#### Exercici 4

**Rest en Destructuring:** Crea una array amb diversos elements. Utilitza destructuring i l'operador rest per a assignar els primers dos elements a variables, i després assignar la resta dels elements a una tercera variable.
```js
const arr = [4, 5, 6, 7, 8, 9, 12];
let [var1, var2, ...var3] = arr;
console.log( var1 );
console.log( var2 );
console.log( var3 );
```

### ![Nivell 3](img/estrella3.svg) Nivell 3

#### Exercici 5

**Spread en Funcions:** Crea una funció que accepti tres arguments. Després, crea una array amb tres elements i crida la funció utilitzant l'operador spread amb aquesta array.

```js
const arr = ['a', 'b', 'c']
function ejercicio5( arg1, arg2, arg3 ) {
 console.log( { arg1 } );
 console.log( { arg2 } );
 console.log( { arg3 } );
```

#### Exercici 6
**Fusionant Objectes amb Spread:** Crea dos objectes amb propietats diferents.Utilitza l'operador spread per a fusionar aquests dos objectes en un de nou.

```js
const objecte1 = {
 nom: 'Ana',
 sexo: 'Femenino',
 estadoCivil: 'Soltera'
};

const objecte2 = {
 pais: 'España',
 Edad: 28,
};

const objeto3 = { ...objecte1, ...objecte2 };
console.log( objeto3 );
```

<br>

[![Anar a Inici](img/arrow-up-in-a-circle.png)](#s21-exercicis-bàsics 'Anar a Inici')

<br>

---

## Bloc 1.5: Array transformations

### ![Nivell 1](img/estrella1.svg)Nivell 1

#### Exercici 1
**Map:** Teniu un array de números[1, 2, 3, 4].Crea una nova array que contingui el quadrat de cada número.

```js
const numeros = [1, 4, 9, 16];

const nuevoArray = numeros.map( ( numero ) => numero * 2 );

console.log( nuevoArray );
```

#### Exercici 2
**Filter:** Teniu una array de números[1, 2, 3, 4].Crea una nova array que només contingui els números parells.

```js
const numbers = [1, 2, 3, 4];
const newArray = numbers.filter( ( evenNumbers ) => evenNumbers % 2 === 0 );
console.log( newArray );
```

#### Exercici 3
**Find:** Teniu una array de números[1, 10, 8, 11].Utilitza la funció find per a trobar el primer número que és major a 10.

```js
const numbers = [1, 10, 8, 11];

const found = numbers.find( ( number ) => number > 10 );

console.log( found );
```

#### Exercici 4

**Reduce:** Teniu una array de números[13, 7, 8, 21].Fes servir la funció reduce per a calcular la suma total dels números.

```js
const array1 = [13, 7, 8, 21];

const sumWithInitial = array1.reduce( ( accumulator, currentValue ) => accumulator + currentValue, 0 );

console.log( sumWithInitial );
```

### ![Nivell 2](img/estrella2.svg) Nivell 2

#### Exercici 5

**Combinar mètodes:** Donat un array "[ 1, 3, 7, 10 ,15, 17, 11, 5, 8, 12, 9 ]", crea una funció en una sola línia que faci el següent:

* Filtra els nombres majors o iguals a 10.
* Multiplica cada nombre filtrat per 2.
* Calcula la suma dels nombres filtrats i multiplicats per 2.
* La funció ha de retornar el resultat de la suma.

```js
const arr = [1, 3, 7, 10, 15, 17, 11, 5, 8, 12, 9];
const resultado = arr
  .filter((num) => num >= 10)
  .map((num) => num * 2)
  .reduce((accumulator, currentValue) => accumulator + currentValue, 0) * 2;

console.log(resultado);
```

### ![Nivell 3](img/estrella3.svg) Nivell 3

#### Exercici 6

**Every / Some:** Usa every i some per a determinar si tots o alguns dels elements de l'array [11, 12, 13, 14] són majors que 10, respectivament

**_Método Every_**

```js
const mayoresQue10 = ( currentValue ) => currentValue > 10;

const array = [11, 12, 13, 14];

console.log( array.every( mayoresQue10 ) );
```

**_Método Some_**

```js
const mayoresQue10Some = ( currentValue ) => currentValue > 10;
const array = [11, 12, 13, 14];
console.log( array.some( mayoresQue10Some ) );
```

<br>

[![Anar a Inici](img/arrow-up-in-a-circle.png)](#s21-exercicis-bàsics 'Anar a Inici')

<br>

---

## Bloc 1.6: Array loops

### ![Nivell 1](img/estrella1.svg) Nivell 1

#### Exercici 1

**forEach:** Teniu una array de noms.Utilitza forEach per a imprimir cada nom a la consola: let noms = ['Anna', 'Bernat', 'Clara'];
```js
let noms = ['Anna', 'Bernat', 'Clara'];
noms.forEach( ( nom ) => console.log( { nom } ) );
```

#### Exercici 2
**for-of:** Teniu una array de noms.Utilitza un bucle 
for-of per a imprimir cada nom a la consola: let noms = ['Anna', 'Bernat', 'Clara'];

```js
let noms = ['Anna', 'Bernat', 'Clara'];
for ( let nom of noms ) {
 console.log( { nom } );
};
``` 

#### Exercici 3

**filter:** Teniu una array de números.Utilitza filter per a crear una nova array que només contingui els números parells.let numeros = [1, 2, 3, 4, 5, 6];

```js
let numeros = [1, 2, 3, 4, 5, 6];
const numerosPares = numeros.filter( ( num ) => num % 2 === 0 );
console.log( { numerosPares } );
```

### ![Nivell 2](img/estrella2.svg) Nivell 2

#### Exercici 4
**for-in:** Teniu un objecte amb parells clau - valor: let obj = { nom: Ona, edat: 25, ciutat: 'Barcelona' }; Utilitza un bucle for-in per a imprimir a la consola cada clau i el seu valor corresponent.

```js
let obj = { nom: 'Ona', edat: 25, ciutat: 'Barcelona' }
for ( let index in obj ) {
 console.log( `${index}: ${obj[index]}` );
}
```

#### Exercici 5

**for-of amb break:** Teniu una array de números.Utilitza un bucle for-of per a imprimir a la consola els números fins a trobar el número 5, llavors atura el bucle: let numeros = [1, 2, 3, 4, 5, 6];

```js
let numeros = [1, 2, 3, 4, 5, 6];
for ( let num of numeros ) {
 if ( num === 5 ) { break; };
 console.log( { num } );
}
console.log( 'El número 5 ha sido encontrado' );
```

### ![Nivell 3](img/estrella3.svg) Nivell 3
#### Exercici 6
**for-of amb index:** Utilitza un bucle for-of per a imprimir a la consola cada element de l'array i la seva posició (index): let noms = ['Anna', 'Bernat', 'Clara']

```js
let noms = ['Anna', 'Bernat', 'Clara'];
for (let [index, nom] of noms.entries()) {
    console.log(`Posició ${index}: ${nom}`);
}
```

<br>

[![Anar a Inici](img/arrow-up-in-a-circle.png)](#s21-exercicis-bàsics 'Anar a Inici')

<br>

---

## Bloc 1.7: Promises & Async / Await

### ![Nivell 1](img/estrella1.svg) Nivell 1

#### Exercici 1

**Creació d'una Promesa:** Crea una promesa que es resolgui després de 2 segons i que retorni la cadena de text 'Hola, món'.

```js
const promesaHolaMon = new Promise( ( resolve, reject ) => {
 setTimeout( () => {
  resolve( {
   mensaje: 'Hola, món'
  } );
 }, 2000 );
} );

promesaHolaMon
 .then( obj => {
  console.log( obj.mensaje );
 } )
 .catch( err => console.error( err ) );
 ```

#### Exercici 2

**Utilització d'una Promesa:** Utilitza la promesa creada en l'exercici anterior.Crea un.then que imprimeixi el resultat a la consola.

```js
const promesaHolaMon = new Promise( ( resolve, reject ) => {
 setTimeout( () => {
  resolve( {
   mensaje: 'Hola, món'
  } );
 }, 2000 );
} );

promesaHolaMon
 .then( obj => {
  console.log( obj.mensaje );
 } )
 .catch( err => console.error( err ) );
 ```

 #### Exercici 3

 **Promesa amb reject:** Crea una promesa que es resolgui després de 2 segons si l'input és igual a 'Hola', i que la rebutgi si l'input és qualsevol altra cosa.

 ```js
 function promesaAmbReject( input ) {
 return new Promise( ( resolve, reject ) => {
  setTimeout( () => {
   ( input === 'Hola' )
    ? resolve( 'Promesa resuelta' )
    : reject( 'Promesa rechazada' );
  }, 2000 );
 } );
}

promesaAmbReject( 'Hola' )
 .then( resultado => {
  console.log( resultado );
 } )
 .catch( err => console.error( err ) );
 ```

 #### Exercici 4

**Ús de async / await:** Escriu una funció asíncrona que utilitzi la funció await per a esperar el resultat de la promesa creada a l'exercici 1, i que després imprimeixi aquest resultat a la consola.

 ```js
 const promesaHolaMon = new Promise( ( resolve, reject ) => {
 setTimeout( () => {
  resolve( {
   result: 'Hola, món'
  } );
 }, 2000 );
} );

const funcionAsincrona = async () => {
 try {
  let resultado = await promesaHolaMon;
  console.log( resultado.result );
 } catch ( err ) {
  console.error( err );
 }
};

funcionAsincrona();
```

### ![Nivell 2](img/estrella2.svg) Nivell 2

#### Exercici 5

**Gestió d'errors amb async/await:** Modifica la funció de l'exercici 4 per a que capturi qualsevol possible error utilitzant un bloc try/catch.

```js
const promesaHolaMon = new Promise( ( resolve, reject ) => {
 setTimeout( () => {
  resolve( 'Hola, món' );
 }, 2000 );
} );

const funcionAsincrona = async () => {
 try {
  let resultado = await promesaHolaMon;
  console.log( resultado );
 } catch ( err ) {
  console.error( err );
 }
};

funcionAsincrona();
```

### ![Nivell 3](img/estrella3.svg) Nivell 3

**Promise.all:** Crea dues promeses que es resolguin després de 2 i 3 segons, respectivament.Utilitza Promise.all per a esperar que ambdues promeses es resolguin, i imprimeix els resultats a la consola.

```js
const promesa1 = new Promise( ( resolve ) => {
 setTimeout( ( () => {
  resolve( 'Primera promesa resuelta después de 2 segundos' );
 } ), 2000 );
} );

const promesa2 = new Promise( ( resolve ) => {
 setTimeout( ( () => {
  resolve( 'Segunda promesa resuelta después de 3 segundos' );
 } ), 3000 );
} );

Promise.all( [promesa1, promesa2] )
 .then( ( resultados ) => {
  console.log( resultados );
 } )
 .catch( ( err ) => {
  console.error( err );
 } );


Promise.allSettled
```

<br>

[![Anar a Inici](img/arrow-up-in-a-circle.png)](#s21-exercicis-bàsics 'Anar a Inici')

<br>
