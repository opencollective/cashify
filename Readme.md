G
Cashify 💸
Biblioteca de conversión de moneda ligera, sucesora de money.js

Estado de construcción Estado de cobertura Estilo de código XO instalar tamaño tamaño minificado

Este paquete se creó porque la biblioteca popular money.js es:

no mantenido (la última confirmación fue hace ~ 5 años)
tiene más de 20 problemas abiertos
no es compatible con TypeScript
tiene globales implícitas
no tiene pruebas unitarias
Destacar
API simple
0 dependencias
Mantenido activamente
Bien probado
Fácil migración desde money.js
Escrito en TypeScript
Instalar en pc
$ npm install cashify
Uso
const  { Cashify }  =  require ( 'cashify' ) ;

 tasas  constantes =  { 
	GBP : 0.92 , 
	EUR : 1.00 , 
	USD : 1.12 
} ;

const  cashify  =  new  Cashify ( { base : 'EUR' , tarifas } ) ;

 resultado  constante =  cobrar . convertir ( 10 ,  { de : 'EUR' ,  a : 'GBP' } ) ;

consola . log ( resultado ) ;  // => 9.2
CashifyNo es necesario utilizar el constructor. En su lugar, puede utilizar la convertfunción:

const  { convertir }  =  require ( 'cobrar' ) ;

 tasas  constantes =  { 
	GBP : 0.92 , 
	EUR : 1.00 , 
	USD : 1.12 
} ;

 resultado  constante =  convertir ( 10 ,  { de : 'EUR' ,  a : 'GBP' ,  base : 'EUR' , tarifas } ) ;

consola . log ( resultado ) ;  // => 9.2
API
Cashify ({base, rates})
Constructor

base
Tipo: string

Moneda base

tarifas
Tipo: object

Objeto que contiene tipos de cambio (por ejemplo, de una API, como tipos de cambio abiertos)

convertir (cantidad, {desde, hasta}) with constructor
Devuelve el resultado de la conversión ( number)

cantidad
Tipo: number

Cantidad de dinero que desea convertir

de
Tipo: string

Moneda a partir de la cual desea convertir

a
Tipo: string

Moneda a la que desea convertir

convertir (cantidad, {desde, hasta, base, tarifas}) without constructor
Devuelve el resultado de la conversión ( number)

cantidad
Tipo: number

Cantidad de dinero que desea convertir

de
Tipo: string

Moneda a partir de la cual desea convertir

a
Tipo: string

Moneda a la que desea convertir

base
Tipo: string

Moneda base

tarifas
Tipo: object

Objeto que contiene tipos de cambio (por ejemplo, de una API, como tipos de cambio abiertos)

Migrar desde money.js
Con Cashifyconstructor:

- const fx = require ('dinero'); 
+ const {Cashify} = require ('cobrar');

- fx.base = 'EUR'; 
- fx.rates = { 
- 	GBP: 0,92, 
- 	EUR: 1,00, 
- 	USD: 1,12 
- };

+ tasas constantes = { 
+ 	 GBP: 0.92, 
+ 	 EUR: 1.00, 
+ 	 USD: 1.12 
+ };

+ const cashify = new Cashify ({base: 'EUR', tarifas});

- fx.convert (10, {desde: 'GBP' hasta: 'EUR'}); 
+ cashify.convert (10, {de: 'GBP', a: 'EUR'});
Con convertfunción:

- const fx = require ('dinero'); 
+ const {convertir} = requerir ('cobrar');

- fx.base = 'EUR'; 
- fx.rates = { 
- 	GBP: 0,92, 
- 	EUR: 1,00, 
- 	USD: 1,12 
- };

+ tasas constantes = { 
+ 	 GBP: 0.92, 
+ 	 EUR: 1.00, 
+ 	 USD: 1.12 
+ };

- fx.convert (10, {desde: 'GBP' hasta: 'EUR'}); 
+ convertir (10, {de: 'GBP', a: 'EUR', base: 'EUR', tarifas});
Proyectos relacionados
Si desea manejar cosas, como el formato de moneda, le recomiendo verificar los siguientes proyectos (funcionan muy bien con Cashify 🦄):

currency.js
Licencia
MIT © Antoni Kepinski
