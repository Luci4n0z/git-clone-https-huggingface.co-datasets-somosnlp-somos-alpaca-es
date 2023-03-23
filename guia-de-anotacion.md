# Guía de anotación

El objetivo de este proyecto de anotación es identificar textos de calidad del dataset de `somos-alpaca-es` y descartar aquellos que 
contengan incorrecciones o incoherencias.

Cada texto consta de 3 campos:
- **1-Instruction**: Detalle de la tarea a completar o pregunta que resolver.
- **2-Input**: El objeto sobre el que se desarrollará la tarea. Este campo podrá estar vacío.
- **3-Output**: La respuesta a la tarea/pregunta.

Esta tarea se ha ideado como una clasificación de texto de una sola etiqueta. El anotador tendrá que escoger *solamente UNA* de las etiquetas 
mencionadas en esta guía: la que mejor describa la razón principal por la que descartar ese texto. 

Podéis apoyaros en el orden en el que aparecen las etiquetas abajo y utilizarlo como jerarquía para elegir la etiqueta que mejor convenga. 
Por ejemplo, si se podrían aplicar tanto BAD INPUT como BAD OUTPUT al mismo texto, es preferible escoger BAD INPUT.

En caso de duda o de que parezca que ninguna etiqueta es del todo apropiada, es mejor **NO** anotar el texto.
Para estos casos recomendamos que el anotador seleccione `Discard` (en Argilla).

Para cualquier duda o pregunta, podéis dirigiros al canal de discord `alpaca-es` en el servidor de Somos NLP.

## Etiquetas

### BAD INSTRUCTION
Esta etiqueta se utilizará cuando la instrucción no sea coherente o contenga errores.

Estos son algunos ejemplos de instrucciones válidas e inválidas:

❌ 1-Instruction: Clasifica el siguiente titular entre las siguientes categorías: política, deportes, internacional. 
El output deberá ser true o false.

✅ 1-Instruction: ¿Quién era el presidente de Canadá en el año 1998? (En este caso la instrucción no necesitará *input*)

✅ 1-Instruction: Hazme un resumen del siguiente texto. (En este caso esperamos que a la instrucción le siga un *input*)


### BAD INPUT
Esta etiqueta se utilizará en los siguientes supuestos:
- Cuando la instrucción requiere de un *input* para poder completarla y el campo aparece vacío.
- Cuando la instrucción no requiere de un *input* y sin embargo este campo tiene contenido.
- Cuando se proporcione un *input* que no sea coherente con la instrucción o contenga errores.

Estos son algunos ejemplos de *input* válido e inválido:


### BAD OUTPUT
Utilizar esta etiqueta si el resultado no es coherente con la intrucción + *input* proporcionados o en el caso de que contenga errores.
**IMPORTANTE** En el caso de este dataset un error sería que el *output* no siguiera la variedad del español que aparezca en la instrucción 
o el *input*, por ejemplo si la instrucción usa *usted* y la respuesta *tú*.

### INAPPROPRIATE
Utilizar esta etiqueta si todos los campos anteriores son correctos y coherentes pero el contenido puede ser considerado inapropiado o 
peligroso, por ejemplo contenido violento, sexual, de odio, etc.

### BIASED
Utilizar esta etiqueta si todos los campos anteriores son correctos y coherentes pero el contenido de los mismos reproduce ideas sesgadas, 
ya sean machistas, racistas, estereotipos, etc.

### ALL GOOD
Utilizar esta etiqueta siempre y cuando no se haya utilizado ninguna de las anteriores, es decir, cuando todos los campos sean coherentes 
y no contengan incorrecciones o contenido inapropiado o sesgado.
