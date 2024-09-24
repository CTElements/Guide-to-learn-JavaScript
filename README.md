# Variavel 
`var`
A instrução var declara variáveis ​​com escopo de função ou com escopo global, opcionalmente inicializando cada uma com um valor.
```` javascript
var x = 1;
if (x === 1) {
  var x = 2;
  console.log(x);
  // Expected output: 2
}
console.log(x);
// Expected output: 2

var x = 10;
var y = 20;

console.log(x);
console.log(y);

console.log(x + y);
console.log(50 * x * y);

// Expected output:10
// Expected output:20
// Expected output:30
// Expected output:10000

```` 

`let`
A declaração let declara variáveis ​​locais reatribuíveis com escopo de bloco, opcionalmente inicializando cada uma com um valor.
````javascript
let x = 1;

if (x === 1) {
  let x = 2;

  console.log(x);
  // Expected output: 2
}
console.log(x);
// Expected output: 1
````
`const`
A declaração const declara variáveis ​​locais com escopo de bloco. O valor de uma constante não pode ser alterado por meio de reatribuição usando o operador de atribuição, mas se uma constante for um objeto, suas propriedades poderão ser adicionadas, atualizadas ou removidas.
````javascript
const number = 42;

try {
  number = 99;
} catch (err) {
  console.log(err);
  //Saída esperada: TypeError: atribuição inválida para const 'number'
  // (Nota: a saída exata pode depender do navegador)
}

console.log(number);
// Expected output: 42
````

# Hoisting
JavaScript Hoisting refere-se ao processo pelo qual o intérprete parece mover a declaração de funções, variáveis, classes ou importações para o topo de seu escopo, antes da execução do código.



````javascript
const x = 1;
{
  console.log(x); // ReferenceError
  const x = 2;
}

//Expected output: Uncaught ReferenceError: Cannot access 'x' before initialization

{
  var x = 1;
}
console.log(x); 
//Expected output: 1

````

# Declaration and initialization
````javascript
let x;
console.log(x); 
//Expected output: "undefined"

let y= 10;
console.log(y); 
//Expected output: 10

const n; // SyntaxError: Missing initializer in const declaration
const d = 10
//Expected output: 10
````
````javascript
if (Math.random() > 0.5) {
  const y = 5;
}
console.log(y); // ReferenceError: y is not defined

if (true) {
  var x = 5;
}
console.log(x); // x is 5

console.log(x); // ReferenceError
const x = 3;

console.log(y); // ReferenceError
let y = 3;
````
````javascript
{
     var t = 20
     let p = 110;
     const q = 111;
}
console.log(t); // 20
console.log(p); // Uncaught ReferenceError: p is not defined
console.log(q); // Uncaught ReferenceError: q is not defined
````

# strings

````javascript
const string1 = "A string primitive";
const string2 = 'Also a string primitive';
const string3 = `Yet another string primitive`;

const string4 = new String("A String object");
"cat".charAt(1); // gives value "a"
"cat"[1]; // gives value "a"

const strPrim = "foo"; // A literal is a string primitive
const strPrim2 = String(1); // Coerced into the string primitive "1"
const strPrim3 = String(true); // Coerced into the string primitive "true"
const strObj = new String(strPrim); // String with new returns a string wrapper object.

console.log(typeof strPrim); // "string"
console.log(typeof strPrim2); // "string"
console.log(typeof strPrim3); // "string"
console.log(typeof strObj); // "object"

const s1 = "2 + 2"; // creates a string primitive
const s2 = new String("2 + 2"); // creates a String object
console.log(eval(s1)); // returns the number 4
console.log(eval(s2)); // returns the string "2 + 2"
````

# undefined

````javascript
function test(t) {
  if (t === undefined) {
    return 'Undefined value!';
  }
  return t;
}

let x;

console.log(test(x));
// Expected output: "Undefined value!"
````

# number

````javascript
let num1 = 255; // integer
let num2 = 255.0; // floating-point number with no fractional part
let num3 = 0xff; // hexadecimal notation
let num4 = 0b11111111; // binary notation
let num5 = 0.255e3; // exponential notation

console.log(num1 === num2); // true
console.log(num1 === num3); // true
console.log(num1 === num4); // true
console.log(num1 === num5); // true
````

# boolean
````javascript
if (new Boolean(true)) {
  console.log("This log is printed.");
}

if (new Boolean(false)) {
  console.log("This log is ALSO printed.");
}

const myFalse = new Boolean(false); // myFalse is a Boolean object (not the primitive value false)
const g = Boolean(myFalse); // g is true
const myString = new String("Hello"); // myString is a String object
const s = Boolean(myString); // s is true
````

# null
````javascript
if (v === null) {
  // Handle `null` case here
}
v == null;

// Equivalent:
v === null || v === undefined;
let v = 42;

v.test; // undefined

v = null;
v.test; // Throws `TypeError: Cannot read property 'test' of null`

v = undefined;
v.test; // Throws `TypeError: Cannot read property 'test' of undefined`

2 + null; // 2
null + 2; // 2

2 - null; // 2
null - 2; // -2

2 * null; // 0
null * 2; // 0

2 ** null; // 1
0 ** 2; // 0

null / 2; // 0

2 + undefined; // NaN
2 * undefined; // NaN
2 - undefined; // NaN
2 ** undefined; // NaN

typeof null; // 'object'
````

# Objects
````javascript
let user = {     // an object
  name: "John",  // by key "name" store value "John"
  age: 30        // by key "age" store value 30
};

// get property values of the object:
alert( user.name ); // John
alert( user.age ); // 30

user.isAdmin = true; //O valor pode ser de qualquer tipo. Vamos adicionar um booleano:

delete user.age; //Para remover uma propriedade, podemos usar o operador delete:

// link para saber mais sobre objeto
//https://javascript.info/object

````

# typeof
````javascript
console.log(typeof 42);
// Expected output: "number"

console.log(typeof 'blubber');
// Expected output: "string"

console.log(typeof true);
// Expected output: "boolean"

console.log(typeof undeclaredVariable);
// Expected output: "undefined"

// link: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof
````

# JSON
JavaScript Object Notation (JSON) é um formato padrão baseado em texto para representar dados estruturados com base na sintaxe de objeto JavaScript.
````javascript

  {
    "name": "Molecule Man",
    "age": 29,
    "secretIdentity": "Dan Jukes",
    "powers": ["Radiation resistance", "Turning tiny", "Radiation blast"]
  },
  {
    "name": "Madame Uppercut",
    "age": 39,
    "secretIdentity": "Jane Wilson",
    "powers": [
      "Million tonne punch",
      "Damage resistance",
      "Superhuman reflexes"
    ]
  }


````
