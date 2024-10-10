# MiguelEjercicios
#Ejercicios de Miguel Angel
#1. Dada una lista de palabras, crea una función que devuelva un diccionario con la cantidad de veces que aparece cada palabra.
def contar_pal(palabras):
    from collections import Counter
    return dict(Counter(palabras))
palabras = ["python", "java", "python", "c++"]
print(contar_pal(palabras))  

#2. Escribe una función que combine dos diccionarios, sumando los valores de las claves comunes.
def combinar_diccionarios(dic1, dic2):
    resultado = dic1.copy()
    for clave, valor in dic2.items():
        resultado[clave] = resultado.get(clave, 0) + valor
    return resultado
dic1 = {'a': 1, 'b': 2}
dic2 = {'b': 3, 'c': 4}
print(combinar_diccionarios(dic1, dic2))  

#3. Dada una lista de números, devuelve un diccionario con la frecuencia de cada número.
def frecuencia_numeros(numeros):
    from collections import Counter
    return dict(Counter(numeros))
numeros = [1, 1, 2, 3, 3, 3]
print(frecuencia_numeros(numeros)) 

#4. Crea una función que reciba una lista de palabras y un número entero, devolviendo una nueva lista con palabras que tienen más de ese número de caracteres.
def filtrar_palabras(palabras, longitud):
    return [palabra for palabra in palabras if len(palabra) > longitud]
palabras = ["hola", "mundo", "python", "programación"]
print(filtrar_palabras(palabras, 5))  

#5. Dada una lista de tuplas, crea una función que devuelva una lista con las tuplas invertidas.
def invertir_tuplas(tuplas):
    return [(b, a) for a, b in tuplas]
tuplas = [(1, 2), (3, 4), (5, 6)]
print(invertir_tuplas(tuplas))  

#6. Dada una lista de números, crea una función que encuentre y devuelva el número que aparece con mayor frecuencia.
def valor_frecuente(numeros):
    from collections import Counter
    return Counter(numeros).most_common(1)[0][0]
numeros = [1, 2, 3, 1, 2, 1]
print(valor_frecuente(numeros))  

#7. Escribe una función que determine si un conjunto es un subconjunto de otro.
def es_subconjunto(conjunto1, conjunto2):
    return conjunto1.issubset(conjunto2)
conjunto1 = {1, 2, 3}
conjunto2 = {1, 2, 3, 4, 5}
print(es_subconjunto(conjunto1, conjunto2))  

#8. Dada una lista de diccionarios que representan personas (con claves "nombre" y "edad"), agrúpalos por edad.
def agrupar_edad(personas):
    from collections import defaultdict
    agrupado = defaultdict(list)
    for persona in personas:
        agrupado[persona['edad']].append(persona['nombre'])
    return dict(agrupado)
personas = [{"nombre": "Ana", "edad": 25}, {"nombre": "Luis", "edad": 25}, {"nombre": "Carlos", "edad": 30}]
print(agrupar_edad(personas)) 

#9.  Implementa el algoritmo Merge Sort para ordenar una lista de números.
def merge_sort(numeros):
    if len(numeros) <= 1:
        return numeros
    medio = len(numeros) // 2
    izquierda = merge_sort(numeros[:medio])
    derecha = merge_sort(numeros[medio:])
    return sorted(izquierda + derecha)
numeros = [5, 3, 8, 6, 2]
print(merge_sort(numeros))

#10. Crea una función que reciba una lista y elimine todos los elementos que sean menores que un valor dado.
def eliminar_menores(numeros, limite):
    return [num for num in numeros if num >= limite]
numeros = [1, 2, 3, 4, 5]
print(eliminar_menores(numeros, 3)) 

#11. Dada una lista que contiene otras listas, crea una función que "aplane" la lista, es decir, devuelva una sola lista con todos los elementos.
def aplanar_lista(lista_de_listas):
    return [elemento for sublista in lista_de_listas for elemento in sublista]
lista_de_listas = [[1, 2], [3, 4], [5]]
print(aplanar_lista(lista_de_listas)) 

#12. Crea una función que calcule la mediana de una lista de números.
def calcular_mediana(numeros):
    numeros_ordenados = sorted(numeros)
    n = len(numeros_ordenados)
    mitad = n // 2
    if n % 2 == 0:
        return (numeros_ordenados[mitad - 1] + numeros_ordenados[mitad]) / 2
    else:
        return numeros_ordenados[mitad]
numeros = [1, 3, 2, 4, 5]
print(calcular_mediana(numeros))  

#13.Dada una lista de números, crea una función que devuelva una nueva lista donde cada número se duplique.
def duplicar_elementos(numeros):
    return [num for num in numeros for _ in range(2)]
numeros = [1, 2, 3]
print(duplicar_elementos(numeros))  

#14. Dada una lista de frases, crea una función que devuelva un diccionario con la cantidad de palabras en cada frase.
def contar_palabras(frases):
    return {i: len(frase.split()) for i, frase in enumerate(frases)}
frases = ["Hola mundo", "Python es genial", "Me gusta programar"]
print(contar_palabras(frases)) 

#15.  Crea una función que encuentre la clave con el valor máximo en un diccionario.
def clave_max(diccionario):
    return max(diccionario, key=diccionario.get)
diccionario = {'a': 10, 'b': 20, 'c': 5}
print(clave_max(diccionario)) 

#16. Escribe una función que devuelva una lista de palabras que son palíndromos de una lista dada.
def encontrar_palindromos(palabras):
    return [palabra for palabra in palabras if palabra == palabra[::-1]]
palabras = ["ana", "oso", "hola", "level"]
print(encontrar_palindromos(palabras))  
