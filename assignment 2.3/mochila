
def mochila(vals,wts,capacidade):
    w = capacidade +1
    h = len(vals)

    tabela = [[0 for x in range(w)] for y in range(h)]


    #Iterando nas linhas
    for index in range(h):
        #iterando nas colunas
        for weight in range(w):
            # Se o item nao cabe na mochila
            if wts[index] > weight:
                tabela[index][weight] = tabela[index - 1][weight]
                continue
        
            # ise o item cabe na mochila
            prior_value = tabela[index - 1][weight]
            #val of current item  + val of remaining weight
            remain_value = tabela[index - 1][weight - wts[index]]
            new_value = vals[index] + remain_value
            tabela[index][weight] = max(prior_value, new_value)

    solution = tabela[h-1][w-1]
    for i in tabela:
        print(i)
    return solution


#Leitura de arquivos
def readentry(filename):
    ordem = list()
    filex= open(filename,'r')
    list_items = filex.readlines()

    for item in list_items:
        value = item.split("\n")
        value = value[:-1]
        for item2 in value:
            value2 = item2.split(" ")
            #print(value)
            #print(value2)
            ordem.append(value2)
    return ordem

def defitems(ordem):
    vals = list()
    wts = list()
    for item in range(1,len(ordem)):
        aux = int(ordem[item][1])
        vals.append(aux)
        aux = int(ordem[item][0])
        wts.append(aux)
    return (vals,wts)


ordem = readentry("mochila01.txt.txt")

capacidade = int(ordem[0][1])
vals, wts = defitems(ordem)
result = mochila(vals,wts,capacidade)
print(result)
