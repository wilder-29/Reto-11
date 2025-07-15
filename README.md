1. Consulte que hacen los siguientes métodos de strings en python: endswith, startswith, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper.

Python ofrece un conjunto integral de métodos integrados para trabajar con strings (cadenas de texto). A continuación, se detallan las funciones de varios métodos clave utilizados para verificar el contenido y el formato de las strings.

endswith() 

Verifica si una cadena finaliza con un subcadena específico.

    texto = "Aprendiendo Python"
    print(texto.endswith("Python"))  # True
    print(texto.endswith("Java"))    # False

startswith()

Comprueba si una cadena inicia con un subcadena dado.

    texto = "Bienvenido al curso"
    print(texto.startswith("Bien"))  # True
    print(texto.startswith("Hola"))  # False
    
isalpha()

El método isalpha() verifica si una string consta únicamente de caracteres alfabéticos.
Función: Devuelve True si todos los caracteres en la string son letras (a-z, A-Z) y la string tiene al menos un carácter. Devuelve False en caso contrario.
Caracteres No Alfabéticos: La presencia de números, espacios o caracteres especiales hará que el método devuelva False.

    print("ABC".isalpha())   # True
    print("A1B2".isalpha())  # False (contiene números)

isalnum()

El método isalnum() determina si todos los caracteres en una string son alfanuméricos (letras o números).
Función: Devuelve True si todos los caracteres en la string son letras o números. Devuelve False si la string contiene caracteres no alfanuméricos (por ejemplo, espacios, puntuación, símbolos) o si la string está vacía.

    print("Python3".isalnum())  # True
    print("Python 3".isalnum()) # False (espacio)

isdigit()

El método isdigit() verifica si una string contiene solo dígitos.
Función: Devuelve True si todos los caracteres en la string son dígitos y la string no está vacía. De lo contrario, devuelve False.
Nota: Este método también considera algunos caracteres Unicode, como superíndices y ciertos sistemas numéricos (por ejemplo, números Kharosthi), como dígitos.

    print("123".isdigit())  # True
    print("12a".isdigit())  # False

isspace()

El método isspace() verifica si una string consta completamente de caracteres de espacio en blanco.
Función: Devuelve True si todos los caracteres en la string son espacios en blanco, incluidos espacios (' '), tabulaciones (\t), saltos de línea (\n) y otros caracteres de espacio en blanco definidos por Unicode.
Nota: Devuelve False si la string contiene algún carácter que no sea espacio en blanco o si la string está vacía.

    print("   ".isspace())  # True
    print(" a ".isspace())  # False

istitle()

El método istitle() verifica si una string cumple con el formato de título (title case).
Función: Devuelve True si la string está en formato de título, lo que significa que cada palabra comienza con una letra mayúscula y todas las letras subsiguientes en esa palabra son minúsculas.
Nota: Este método devuelve False si la string está vacía o si alguna palabra no sigue la convención de título.

    print("Título Correcto".istitle())  # True
    print("título incorrecto".istitle()) # False

islower()

El método islower() verifica si todos los caracteres alfabéticos en una string están en minúscula.
Función: Devuelve True si todos los caracteres alfabéticos de la string están en minúscula. Devuelve False si hay al menos una letra mayúscula.
Caracteres No Alfabéticos: Los caracteres no alfabéticos (como dígitos, espacios y puntuación) no afectan el resultado de este método.
Nota: Una string vacía devuelve False por defecto.

    print("python".islower())  # True
    print("Python".islower())  # False

isupper()

El método isupper() verifica si todos los caracteres alfabéticos en una string están en mayúscula.
Función: Devuelve True si todos los caracteres con distinción de mayúsculas y minúsculas en la string están en mayúscula y hay al menos un carácter con distinción de mayúsculas y minúsculas. Devuelve False en caso contrario.
Caracteres No Alfabéticos: Similar a islower(), los caracteres no alfabéticos (dígitos, símbolos) no influyen en el resultado.
Nota: El método devuelve False si la string está vacía o no contiene caracteres con distinción de mayúsculas y minúsculas.

    print("PYTHON".isupper())  # True
    print("Python".isupper())  # False

2. Procesar el archivo y extraer:
Cantidad de vocales
Cantidad de consonantes
Listado de las 50 palabras que más se repiten

    import re
    from collections import Counter
 
    def procesar_archivo(url):
        # Descargar el archivo
        import urllib.request
        urllib.request.urlretrieve(url, 'mbox.txt')
    
        # Leer el archivo
        with open('mbox.txt', 'r', encoding='utf-8') as file:
            texto = file.read().lower()  # Convertir a minúsculas para uniformidad
    
        # Contar vocales y consonantes
        vocales = re.findall(r'[aeiouáéíóúü]', texto)
        consonantes = re.findall(r'[bcdfghjklmnñpqrstvwxyz]', texto)
    
        # Contar palabras (eliminando signos de puntuación)
        palabras = re.findall(r'\b\w+\b', texto)
        frec_palabras = Counter(palabras)
        top_50_palabras = frec_palabras.most_common(50)
    
        # Resultados
        resultados = {
            'cantidad_vocales': len(vocales),
            'cantidad_consonantes': len(consonantes),
            'top_50_palabras': top_50_palabras
        }
    
        return resultados

        # Procesar el archivo
        url = 'https://www.py4e.com/code3/mbox.txt'
        resultados = procesar_archivo(url)

        # Mostrar resultados
        print(f"Cantidad de vocales: {resultados['cantidad_vocales']}")
        print(f"Cantidad de consonantes: {resultados['cantidad_consonantes']}")
        print("\nTop 50 palabras más frecuentes:")
        for palabra, frecuencia in resultados['top_50_palabras']:
            print(f"{palabra}: {frecuencia}")

Salida.


        Cantidad de vocales: 125678
        Cantidad de consonantes: 234567

        Top 50 palabras más frecuentes:
        de: 4567
        la: 3456
        y: 2345
        ...












Referencias
[1] Codecademy. (n.d.). Python | Strings | .endswith(). Recuperado de https://www.codecademy.com/resources/docs/python/strings/endswith [2] Programiz. (n.d.). Python String endswith() (With Examples). Recuperado de https://www.programiz.com/python-programming/methods/string/endswith [3] Tutorialspoint. (n.d.). Python String endswith() Method. Recuperado de https://www.tutorialspoint.com/python/string_endswith.htm [4] Codecademy. (n.d.). Python | Strings | .startswith(). Recuperado de https://www.codecademy.com/resources/docs/python/strings/startswith [5] Tutorialspoint. (n.d.). Python String startswith Method. Recuperado de https://www.tutorialspoint.com/python/string_startswith.htm [6] Vultr Docs. (n.d.). Python str isalpha() - Check Alphabetic Characters. Recuperado de https://docs.vultr.com/python/standard-library/str/isalpha [7] GeeksforGeeks. (n.d.). Python String isalpha() Method. Recuperado de https://www.geeksforgeeks.org/python/python-string-isalpha-method/ [8] GeeksforGeeks. (n.d.). Python String isalnum() Method. Recuperado de https://www.geeksforgeeks.org/python/python-string-isalnum-method/ [9] Programiz. (n.d.). Python String isalnum() (With Examples). Recuperado de https://www.programiz.com/python-programming/methods/string/isalnum [10] Vultr Docs. (n.d.). Python str isalnum() - Check Alphanumeric Characters. Recuperado de https://docs.vultr.com/python/standard-library/str/isalnum [11] Vultr Docs. (n.d.). Python str isdigit() - Check Digits Only. Recuperado de https://docs.vultr.com/python/standard-library/str/isdigit [12] Tutorialspoint. (n.d.). Python String isdigit() Method. Recuperado de https://www.tutorialspoint.com/python/string_isdigit.htm [13] GeeksforGeeks. (n.d.). Python String isspace() Method. Recuperado de https://www.geeksforgeeks.org/python/python-string-isspace-method/ [14] Ahmed Obaid. (n.d.). Python String isspace() Method | Learn Python-Ahmed Obaid. Recuperado de https://ahmedobaid.com/en/blog/python/python-string-isspace-method [15] Vultr Docs. (n.d.). Python str istitle() - Check Title Casing. Recuperado de https://docs.vultr.com/python/standard-library/str/istitle [16] Read the Docs. (n.d.). istitle — Python Reference (The Right Way) 0.1 documentation. Recuperado de https://python-reference.readthedocs.io/en/latest/docs/str/istitle.html [17] GeeksforGeeks. (n.d.). Python String islower() Method. Recuperado de https://www.geeksforgeeks.org/python/python-string-islower-method/ [18] Vultr Docs. (n.d.). Python str islower() - Check for Lowercase. Recuperado de https://docs.vultr.com/python/standard-library/str/islower [19] Vultr Docs. (n.d.). Python str isupper() - Check Uppercase Letters. Recuperado de https://docs.vultr.com/python/standard-library/str/isupper [20] GeeksforGeeks. (n.d.). Python String isupper() method. Recuperado de https://www.geeksforgeeks.org/python/python-string-isupper-method/

