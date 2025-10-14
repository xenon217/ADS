#1
def busca_simples(lista, item):
    for i in range(len(lista)):
        if lista[i] == item:
            return i 



numeros = [10, 20, 30, 40, 50]
print(busca_simples(numeros, 30))  
print(busca_simples(numeros, 99))  

#2
def encontra_menor(arr):
    menor = arr[0]
    menor_indice = 0
    for i in range(1, len(arr)):
        if arr[i] < menor:
            menor = arr[i]
            menor_indice = i
    return menor_indice


def ordenacao_por_selecao(arr):
    novo_arr = []
    for i in range(len(arr)):
        menor = encontra_menor(arr)
        novo_arr.append(arr.pop(menor))
    return novo_arr
    
print(ordenacao_por_selecao([5, 3, 6, 2, 10]))

#3
def busca_binaria(lista, item):
    baixo = 0
    alto = len(lista) - 1

    while baixo <= alto:
        meio = (baixo + alto) // 2
        chute = lista[meio]

        if chute == item:
            return meio
        if chute > item:
            alto = meio - 1
        else:
            baixo = meio + 1
            
    return None

lista = [1, 3, 5, 7, 9]
print(busca_binaria(lista, 3))  
print(busca_binaria(lista, 8)) 
