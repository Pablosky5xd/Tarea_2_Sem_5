import os
productos = []

def añadir_producto():
    nombre= input("ingresar nombre del producto: ")
    while True:
        cantidad= input("ingresar la cantidad: ")
        if cantidad.isdecimal():
            break
        else:
            print("El valor debe ser un numero")
            
    while True:
        precio= input("ingresar precio del producto: ")
        if precio.isdecimal():
            break
        else:
            print("El valor debe ser un numero entero")
    producto= {
        "nombre": nombre, "cantidad": cantidad, "precio": precio
    } 
    productos.append(producto)
    print("producto añadido con exito")

def ver_productos():
    for producto in productos:
        print(f"Nombre: {producto["nombre"]}, Cantidad: {producto["cantidad"]}, Precio: {producto["precio"]}")

def actualizar_producto():
    nombre = input("Ingrese el nombre del producto que desee modificar: ")
    for producto in productos:
        if producto["nombre"] == nombre:
            nombre= input("ingresar nuevo nombre del producto: ")
            if nombre: 
                producto["nombre"] = nombre
            while True:
                cantidad= input("ingresar la nueva cantidad: ")
                if cantidad.isdecimal():
                    producto["cantidad"] = cantidad
                    break
                else:
                    print("El valor debe ser un numero")
                    
            while True:
                precio= input("ingresar nuevo precio del producto: ")
                if precio.isdecimal():
                    producto["precio"] = precio
                    break
                else:
                    print("El valor debe ser un numero entero")
                    
def eliminar_producto():
   nombre = input("ingrese el nombre del producto que desee eliminar: ")
   for producto in productos:
       if producto["nombre"] == nombre:
           productos.remove(producto)
           print("EL prodcuto de elimino correctamente")
def guardar_datos():
    with open("productos.txt", "w") as file:
        for producto in productos:
            file.write(f"{producto["nombre"]}, {producto["cantidad"]}, {producto["precio"]}\n")
    print("Se guardaron los archivos con exito :)")

def cargar_datos():
    with open("productos.txt", "r") as file:
        for linea in file:
            nombre,precio,cantidad = linea.strip().split(",")
            producto= {
                "nombre": nombre, "cantidad": cantidad, "precio": precio
            } 
            productos.append(producto)

def menu():
    cargar_datos()
    while True:
        print("1: Añadir producto")
        print("2: Ver productos")
        print("3: Actualizar producto")
        print("4: Eliminar producto")
        print("5: Guardar datos y salir")

        opcion = input("Selecciona una opción: ")

        if opcion == '1':
            añadir_producto()
        elif opcion == '2':
            ver_productos()
        elif opcion == '3':
            actualizar_producto()
        elif opcion == '4':
            eliminar_producto()
        elif opcion == '5':
            guardar_datos()
            break
        else:
            print("Por favor, selecciona una opción válida.")
            
def generar_txt():
    if not os.path.isfile("productos.txt"):
        with open("productos.txt", "w") as file:
            pass
        print("Se Genero el archivo con exito")
    else: 
        print("El archivo ya existe")

generar_txt()
menu()
