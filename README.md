from pilas import Pila

def ordenar_descendente(pila):
    if pila.es_vacia():
        print("La pila está vacía")
        return None
    else:
        pila_aux = Pila()

        while not pila.es_vacia():
            temp = pila.pop()
            while not pila_aux.es_vacia() and pila_aux.peek() > temp:
                pila.push(pila_aux.pop())
            pila_aux.push(temp)
        while not pila_aux.es_vacia():
            pila.push(pila_aux.pop())

# Ejemplo de uso
pila1 = Pila()
pila1.push(1)
pila1.push(2)
pila1.push(3)
pila1.push(4)
pila1.mostrar()  
ordenar_descendente(pila1)
pila1.mostrar()
