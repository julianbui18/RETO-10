# RETO 10 - MATRICES
1. Desarrolle un programa que permita realizar la suma/resta de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.

**SOLUCION PARA SUMAR MATRICES**
```python
# Esta función pide ingresar los datos de una matriz
def pedir_matriz(nombre_matriz):
    # Pedimos cuántas filas y columnas tiene la matriz
    filas = int(input("Cuántas filas tiene la matriz " + nombre_matriz + ": "))
    columnas = int(input("Cuántas columnas tiene la matriz " + nombre_matriz + ": "))
    print("Ingresar los valores de la matriz " + nombre_matriz + ":")
    matriz = []  # Aquí vamos a guardar toda la matriz
    # Recorremos cada fila
    for fila_actual in range(filas):
        fila_nueva = []  # Lista vacía para guardar los valores de una fila
        # Recorremos cada columna
        for columna_actual in range(columnas):
            mensaje = "Valor en la posición [" + str(fila_actual) + "][" + str(columna_actual) + "]: "
            numero = float(input(mensaje))  # Ingresar numero
            fila_nueva.append(numero)  # Se agrega a la fila
        matriz.append(fila_nueva)  # Se agrega la fila completa a la matriz

    return matriz, filas, columnas  # Se devuelve la matriz y su tamaño

# Esta función muestra en pantalla cualquier matriz
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""  # Cadena para mostrar cada fila
        for valor in fila:
            linea += str(valor) + "  "  # Convertimos cada número a texto y lo agregamos a la línea
        print(linea)  # Mostramos la fila completa

# Esta función suma dos matrices del mismo tamaño
def sumar(matriz1, matriz2):
    resultado = []  # Aquí se guardará la nueva matriz sumada

    # Recorremos cada fila
    for fila_actual in range(len(matriz1)):
        fila_suma = []  # Lista para la fila resultante
        # Recorremos cada columna
        for columna_actual in range(len(matriz1[0])):
            suma = matriz1[fila_actual][columna_actual] + matriz2[fila_actual][columna_actual]
            fila_suma.append(suma)  # Guardamos el resultado de la suma
        resultado.append(fila_suma)  # Agregamos la fila sumada al resultado final

    return resultado  # Devolvemos la matriz con la suma

# Parte principal del codigo
print("Suma de dos matrices")

# Pedimos los datos de ambas matrices
matrizA, filasA, columnasA = pedir_matriz("A")
matrizB, filasB, columnasB = pedir_matriz("B")
# Verificamos que las matrices tengan el mismo tamaño
if filasA != filasB or columnasA != columnasB:
    print("Error: Las matrices deben tener el mismo tamaño.")
else:
    # Hacemos la suma si las dimensiones coinciden
    resultado = sumar(matrizA, matrizB)
    print("La matriz resultado de la suma es:")
    mostrar_matriz(resultado)  # Mostramos el resultado final
```

**SOLUCION PARA RESTAR MATRICES**
```python
# Esta función pide ingresar los datos de una matriz
def pedir_matriz(nombre_matriz):
    # Pedimos cuántas filas y columnas tiene la matriz
    filas = int(input("Cuántas filas tiene la matriz " + nombre_matriz + ": "))
    columnas = int(input("Cuántas columnas tiene la matriz " + nombre_matriz + ": "))
    print("Ingresar los valores de la matriz " + nombre_matriz + ":")
    matriz = []  # Aquí vamos a guardar toda la matriz
    # Recorremos cada fila
    for fila_actual in range(filas):
        fila_nueva = []  # Lista vacía para guardar los valores de una fila
        # Recorremos cada columna
        for columna_actual in range(columnas):
            mensaje = "Valor en la posición [" + str(fila_actual) + "][" + str(columna_actual) + "]: "
            numero = float(input(mensaje))  # Ingresar numero
            fila_nueva.append(numero)  # Se agrega a la fila
        matriz.append(fila_nueva)  # Se agrega la fila completa a la matriz

    return matriz, filas, columnas  # Se devuelve la matriz y su tamaño

# Esta función muestra en pantalla cualquier matriz
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""  # Cadena para mostrar cada fila
        for valor in fila:
            linea += str(valor) + "  "  # Convertimos cada número a texto y lo agregamos a la línea
        print(linea)  # Mostramos la fila completa

# Esta función resta dos matrices del mismo tamaño
def restar(matriz1, matriz2):
    resultado = []  # Aquí se guardará la nueva matriz restada
    # Recorremos cada fila
    for fila_actual in range(len(matriz1)):
        fila_resta = []  # Lista para la fila resultante
        # Recorremos cada columna
        for columna_actual in range(len(matriz1[0])):
            resta = matriz1[fila_actual][columna_actual] - matriz2[fila_actual][columna_actual]
            fila_resta.append(resta)  # Guardamos el resultado de la resta
        resultado.append(fila_resta)  # Agregamos la fila restada al resultado final

    return resultado  # Devolvemos la matriz con la resta

# Parte principal del codigo
print("Resta de dos matrices")
# Pedimos los datos de ambas matrices
matrizA, filasA, columnasA = pedir_matriz("A")
matrizB, filasB, columnasB = pedir_matriz("B")
# Verificamos que las matrices tengan el mismo tamaño
if filasA != filasB or columnasA != columnasB:
    print("Error: Las matrices deben tener el mismo tamaño.")
else:
    # Hacemos la resta si las dimensiones coinciden
    resultado = restar(matrizA, matrizB)
    print("La matriz resultado de la resta es:")
    mostrar_matriz(resultado)  # Mostramos el resultado final
```
2. Desarrolle un programa que permita realizar el producto de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.

**SOLUCION**
```python
# Esta función es para ingresar los datos de una matriz
def pedir_matriz(nombre_matriz):
    filas = int(input("Cuántas filas tiene la matriz " + nombre_matriz + ": "))
    columnas = int(input("Cuántas columnas tiene la matriz " + nombre_matriz + ": "))
    print("Ingresar los valores de la matriz " + nombre_matriz + ":")
    matriz = []
    # Recorremos cada fila
    for fila_actual in range(filas):
        fila_nueva = []
        # Recorremos cada columna
        for columna_actual in range(columnas):
            mensaje = "Valor en la posición [" + str(fila_actual) + "][" + str(columna_actual) + "]: "
            numero = float(input(mensaje))
            fila_nueva.append(numero)
        matriz.append(fila_nueva)

    return matriz, filas, columnas

# Esta función muestra la matriz en pantalla
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""
        for valor in fila:
            linea += str(valor) + "  "
        print(linea)

# Esta función multiplica dos matrices si se pueden multiplicar
def multiplicar_matrices(matriz1, matriz2):
    resultado = []
    # Recorremos las filas de la primera matriz
    for fila_actual in range(len(matriz1)):
        fila_resultado = []

        # Recorremos las columnas de la segunda matriz
        for columna_actual in range(len(matriz2[0])):
            suma = 0  # Acumulador para sumar los productos
            # Se multiplica y se suma según la regla del producto de matrices
            for posicion in range(len(matriz2)):
                valor1 = matriz1[fila_actual][posicion]
                valor2 = matriz2[posicion][columna_actual]
                suma += valor1 * valor2
            fila_resultado.append(suma)
        resultado.append(fila_resultado)

    return resultado

# Parte principál del codigo
print("Multiplicación de dos matrices")
# Ingresar las matrices
matrizA, filasA, columnasA = pedir_matriz("A")
matrizB, filasB, columnasB = pedir_matriz("B")
# Validamos que se puedan multiplicar (columnas de A == filas de B)
if columnasA != filasB:
    print("Error: No se pueden multiplicar. Las columnas de A deben ser iguales a las filas de B.")
else:
    resultado = multiplicar_matrices(matrizA, matrizB)
    print("El resultado de la multiplicación es:")
    mostrar_matriz(resultado)
```
3. Desarrolle un programa que permita obtener la matriz transpuesta de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.

**SOLUCION**
```python
# Esta función es para ingresar los datos de una matriz
def pedir_matriz(nombre_matriz):
    filas = int(input("¿Cuántas filas tiene la matriz " + nombre_matriz + "? "))
    columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre_matriz + "? "))
    print("Ingresar los valores de la matriz " + nombre_matriz + ":")
    matriz = []
    # Recorremos cada fila
    for fila_actual in range(filas):
        fila_nueva = []
        for columna_actual in range(columnas):
            mensaje = "Valor en la posición [" + str(fila_actual) + "][" + str(columna_actual) + "]: "
            numero = float(input(mensaje))
            fila_nueva.append(numero)
        matriz.append(fila_nueva)

    return matriz, filas, columnas

# Esta función muestra una matriz en pantalla
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""
        for valor in fila:
            linea += str(valor) + "  "
        print(linea)

# Esta función calcula la matriz transpuesta
def transponer_matriz(matriz_original):
    filas = len(matriz_original)
    columnas = len(matriz_original[0])
    # Creamos la matriz transpuesta (invirtiendo filas y columnas)
    matriz_transpuesta = []
    for columna_actual in range(columnas):
        nueva_fila = []
        for fila_actual in range(filas):
            valor = matriz_original[fila_actual][columna_actual]
            nueva_fila.append(valor)
        matriz_transpuesta.append(nueva_fila)

    return matriz_transpuesta

# Parte principal
print("Obtener la matriz transpuesta")
# Ingresar una matriz
matriz_usuario, cantidad_filas, cantidad_columnas = pedir_matriz("Original")
# Validamos que la matriz tenga al menos una fila y una columna
if cantidad_filas < 1 or cantidad_columnas < 1:
    print("Error: La matriz debe tener al menos una fila y una columna.")
else:
    # Calculamos la transpuesta
    resultado_transpuesta = transponer_matriz(matriz_usuario)
    print("La matriz original es:")
    mostrar_matriz(matriz_usuario)
    print("Su matriz transpuesta es:")
    mostrar_matriz(resultado_transpuesta)
```

4. Desarrollar un programa que sume los elementos de una columna dada de una matriz.

**SOLUCION**
```python
# Esta función es para ingresar los datos de una matriz
def pedir_matriz(nombre_matriz):
    filas = int(input("¿Cuántas filas tiene la matriz " + nombre_matriz + "? "))
    columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre_matriz + "? "))
    print("Ingresar los valores de la matriz " + nombre_matriz + ":")
    matriz = []
    for fila_actual in range(filas):
        fila_nueva = []
        for columna_actual in range(columnas):
            mensaje = "Valor en la posición [" + str(fila_actual) + "][" + str(columna_actual) + "]: "
            numero = float(input(mensaje))
            fila_nueva.append(numero)
        matriz.append(fila_nueva)

    return matriz, filas, columnas

# Esta función muestra la matriz en pantalla
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""
        for valor in fila:
            linea += str(valor) + "  "
        print(linea)

# Esta función suma los elementos de una columna específica
def sumar_columna(matriz, numero_columna):
    suma = 0
    for fila in matriz:
        suma += fila[numero_columna]

    return suma

# -Parte principal
print("Sumar los elementos de una columna específica de una matriz")
# Pedimos la matriz
matriz_usuario, filas, columnas = pedir_matriz("A")
# Mostramos la matriz para que el usuario se ubique
print("La matriz ingresada es:")
mostrar_matriz(matriz_usuario)

# Ingresar el numero de la columna a sumar
columna_a_sumar = int(input("¿Qué número de columna desea sumar? (Empieza desde 0): "))
# Validamos que la columna exista
if columna_a_sumar < 0 or columna_a_sumar >= columnas:
    print("Error: Esa columna no existe en la matriz.")
else:
    # Calculamos la suma
    resultado = sumar_columna(matriz_usuario, columna_a_sumar)
    print("La suma de los elementos de la columna " + str(columna_a_sumar) + " es: " + str(resultado))
```

5. Desarrollar un programa que sume los elementos de una fila dada de una matriz.

**SOLUCION**
```python
# Esta función es para ingresar los datos de la matriz
def pedir_matriz(nombre_matriz):
    filas = int(input("¿Cuántas filas tiene la matriz " + nombre_matriz + "? "))
    columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre_matriz + "? "))
    print("Ingresar los valores de la matriz " + nombre_matriz + ":")
    matriz = []
    for fila_actual in range(filas):
        fila_nueva = []
        for columna_actual in range(columnas):
            mensaje = "Valor en la posición [" + str(fila_actual) + "][" + str(columna_actual) + "]: "
            numero = float(input(mensaje))
            fila_nueva.append(numero)
        matriz.append(fila_nueva)

    return matriz, filas, columnas

# Esta función muestra la matriz en pantalla
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""
        for valor in fila:
            linea += str(valor) + "  "
        print(linea)

# Esta función suma los elementos de una fila específica
def sumar_fila(matriz, numero_fila):
    fila_elegida = matriz[numero_fila]
    suma = 0

    for valor in fila_elegida:
        suma += valor

    return suma

# Parte principal del codigo
print("Sumar los elementos de una fila específica de una matriz")
# Pedir matriz
matriz_usuario, filas, columnas = pedir_matriz("A")
# Mostramos la matriz para que el usuario la vea
print("La matriz ingresada es:")
mostrar_matriz(matriz_usuario)
# Fila a sumar
fila_a_sumar = int(input("¿Qué número de fila desea sumar? (Empieza desde 0): "))
# Validamos que la fila exista
if fila_a_sumar < 0 or fila_a_sumar >= filas:
    print("Error: Esa fila no existe en la matriz.")
else:
    # Calculamos la suma de esa fila
    resultado = sumar_fila(matriz_usuario, fila_a_sumar)
    print("La suma de los elementos de la fila " + str(fila_a_sumar) + " es: " + str(resultado))
```

**JULIAN ESTEBAN BUITRAGO CRUZ**
