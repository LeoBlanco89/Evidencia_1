# Evidencia_1
Codigo de Vscode para una evidencia de Programacion

def menuPrincipal():
    print("\nMENÚ PRINCIPAL")
    print(" ")
    print("[1] Registrar una venta.")
    print("[2] Consultar una venta")
    print("[3] Salir.")
    print(" ")

def Buscar(clave_buscar,Ventas):
    lista=[]
    for i in Ventas:
        if i[0]==clave_buscar:
            lista.append(i)
    return lista

Ventas=[]
consultas=[]
while (True):
    menuPrincipal()
    opcion = input("¿Qué opción deseas?: ")
    respuesta = 1
    if opcion=="1":
        while respuesta==1:
            Registro=[]
            print("Registrar una Venta\n")
            numero=int(input("Escribe el numero#"))
            descripcion=input("Escribe la descripcion: ")
            cantidad=int(input("Escribe la cantidad: "))
            precio = float(input("Escribe el precio: "))
            Total=cantidad*precio
            Registro.append(numero)
            Registro.append(descripcion)
            Registro.append(cantidad)
            Registro.append(precio)
            Registro.append(Total)
            Ventas.append(Registro)
            respuesta=int(input("¿Quieres registrar otro articulo? (1-Si/0-No)\n"))

    elif opcion=="2":
        pago=0
        clave_buscar=int(input("Escribe la clave a buscar: "))
        consultas=Buscar(clave_buscar,Ventas)
        if consultas:
            for i in consultas:
                print(f"Numero {i[0]}")
                print(f"descripcion {i[1]}")
                print(f"{i[2]}")
                print(f"{i[3]}")
                print(f"{i[4]}")
                pago=pago+i[4]
            print(f"Pago total de la venta {pago}")
        else:
            print("No se ha encontrado")
        consultas.clear
    
    elif opcion=="3":
        print("Saliendo...")
        break
    else:
        print ("\nNo has pulsado ninguna opción correcta...\npulsa una tecla para continuar")
