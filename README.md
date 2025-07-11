1. Consulte que hacen los siguientes métodos de strings en python: endswith, startswith, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper.

Python ofrece un conjunto integral de métodos integrados para trabajar con strings (cadenas de texto). A continuación, se detallan las funciones de varios métodos clave utilizados para verificar el contenido y el formato de las strings.

endswith()

El método endswith() verifica si una string termina con un sufijo específico.
Función: Devuelve True si la string termina con el sufijo proporcionado; de lo contrario, devuelve False.
Parámetros: Acepta el sufijo (una string o una tupla de strings) como argumento obligatorio, y los índices opcionales start y end para definir el rango de búsqueda dentro de la string.
Sensibilidad a Mayúsculas/Minúsculas: Este método distingue entre mayúsculas y minúsculas.

startswith()

El método startswith() verifica si una string comienza con un prefijo específico.
Función: Devuelve True si la string comienza con el prefijo dado; de lo contrario, devuelve False.
Parámetros: Acepta el prefijo (una string o una tupla de strings) como argumento obligatorio, y los índices opcionales start y end para limitar el rango de búsqueda.
Sensibilidad a Mayúsculas/Minúsculas: Este método distingue entre mayúsculas y minúsculas.

isalpha()

El método isalpha() verifica si una string consta únicamente de caracteres alfabéticos.
Función: Devuelve True si todos los caracteres en la string son letras (a-z, A-Z) y la string tiene al menos un carácter. Devuelve False en caso contrario.
Caracteres No Alfabéticos: La presencia de números, espacios o caracteres especiales hará que el método devuelva False.

isalnum()

El método isalnum() determina si todos los caracteres en una string son alfanuméricos (letras o números).
Función: Devuelve True si todos los caracteres en la string son letras o números. Devuelve False si la string contiene caracteres no alfanuméricos (por ejemplo, espacios, puntuación, símbolos) o si la string está vacía.

isalnum()

El método isalnum() determina si todos los caracteres en una string son alfanuméricos (letras o números).
Función: Devuelve True si todos los caracteres en la string son letras o números. Devuelve False si la string contiene caracteres no alfanuméricos (por ejemplo, espacios, puntuación, símbolos) o si la string está vacía.

isdigit()

El método isdigit() verifica si una string contiene solo dígitos.
Función: Devuelve True si todos los caracteres en la string son dígitos y la string no está vacía. De lo contrario, devuelve False.
Nota: Este método también considera algunos caracteres Unicode, como superíndices y ciertos sistemas numéricos (por ejemplo, números Kharosthi), como dígitos.

isspace()

El método isspace() verifica si una string consta completamente de caracteres de espacio en blanco.
Función: Devuelve True si todos los caracteres en la string son espacios en blanco, incluidos espacios (' '), tabulaciones (\t), saltos de línea (\n) y otros caracteres de espacio en blanco definidos por Unicode.
Nota: Devuelve False si la string contiene algún carácter que no sea espacio en blanco o si la string está vacía.

istitle()

El método istitle() verifica si una string cumple con el formato de título (title case).
Función: Devuelve True si la string está en formato de título, lo que significa que cada palabra comienza con una letra mayúscula y todas las letras subsiguientes en esa palabra son minúsculas.
Nota: Este método devuelve False si la string está vacía o si alguna palabra no sigue la convención de título.

islower()

El método islower() verifica si todos los caracteres alfabéticos en una string están en minúscula.
Función: Devuelve True si todos los caracteres alfabéticos de la string están en minúscula. Devuelve False si hay al menos una letra mayúscula.
Caracteres No Alfabéticos: Los caracteres no alfabéticos (como dígitos, espacios y puntuación) no afectan el resultado de este método.
Nota: Una string vacía devuelve False por defecto.

isupper()

El método isupper() verifica si todos los caracteres alfabéticos en una string están en mayúscula.
Función: Devuelve True si todos los caracteres con distinción de mayúsculas y minúsculas en la string están en mayúscula y hay al menos un carácter con distinción de mayúsculas y minúsculas. Devuelve False en caso contrario.
Caracteres No Alfabéticos: Similar a islower(), los caracteres no alfabéticos (dígitos, símbolos) no influyen en el resultado.
Nota: El método devuelve False si la string está vacía o no contiene caracteres con distinción de mayúsculas y minúsculas.


2. Procesar el archivo y extraer:
Cantidad de vocales
Cantidad de consonantes
Listado de las 50 palabras que más se repiten
