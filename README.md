# Gerador-de-CPF

    import random

    boas_vindas = input("Olá! Seja bem vindo a sua geradora de CPF infinita!\nDigite qualquer tecla para conseguir seu primeiro CPF. ")

    while True:


        nove_dig = []
        rst = 0
        mult = 10
    
    
        for _ in range(0,9):
            numero = int(random.randint(0,9))
            nove_dig.append(numero)
            
            rst += numero * mult
            mult -= 1
    
        rst *= 10
        rst %= 11
    
        if rst > 9:
            rst = 0
            nove_dig.append(rst)
        else:
            nove_dig.append(rst)
    
    
        rst = 0 
        mult = 11
        cont = 0
    
        for _ in range(0,10):
            rst += nove_dig[cont] * mult
            cont += 1
            mult -= 1
    
        rst *= 10
        rst %= 11
    
        if rst > 9:
            rst = 0
            nove_dig.append(rst)
        else:
            nove_dig.append(rst)
    
        print("Aqui está seu CPF!")
        for elemento in nove_dig:
            print(elemento, end='')
    
        pergunta = input("\nVocê gostaria de mais um CPF? Digite [S] para sim e [N] para não. ")
        pergunta = pergunta.lower()
    
        if pergunta == "s":
            continue
        elif pergunta == "n":
            print("Tudo bem! Encerrando sistema...")
            break
        else:
            print("Resposta inválida! Encerrando sistema.")
            break




