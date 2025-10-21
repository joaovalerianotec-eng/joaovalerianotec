# joaovalerianotec
Meu primeiro repositório no GitHub
João Pedro Valeriano. Projeto inaugural em desenvolvimento de software. Estudante de Engenharia da Computação, com crescente paixão e dedicação à programação.

print('-=--=-' *15)
print('Bem-Vindo a pizzaria João Pedro Valeriano')
print('-=--=--=--=--=-Cardápio-=--=--=--=--=--=--=--=--=--=---=--=---=--=---=--=--')
print('-=--=-' *15)
print('-=--=--| TAMANHO | PIZZA SALGADA (PS) | PIZZA DOCE (PD) |-=--=--')
print('-=--=--|    P    |     R$30,00        |     R$34,00     |-=--=--')
print('-=--=--|    M    |     R$45,00        |     R$48,00     |-=--=--')
print('-=--=--|    G    |     R$60,00        |     R$66,00     |-=--=--')
print('-=--=-' *15)

# Definição de preços
total = 0.0  # Inicializado como float para acumular valores
psalgada = 30  # Pizza pequena salgada
pdoce = 34  # Pizza pequena doce
msalgada = 45  # Pizza média salgada
mdoce = 48  # Pizza média doce
gsalgada = 60  # Pizza grande salgada
gdoce = 66  # Pizza grande doce

# Sabores das Pizzas
pizzadoce = 'PD'  # Pizza Doce
pizzasalgada = 'PS'  # Pizza Salgada

# Tamanhos das Pizzas
pizzaP = 'P'  # Pizza pequena
pizzaM = 'M'  # Pizza Média
pizzaG = 'G'  # Pizza Grande


# Definição da função para calcular preço
def preco_sabor(tamanho, sabor):
    if tamanho == 'P':  # Pizza pequena
        if sabor == 'PD':  # Doce
            return 34  # Preço da pizza pequena doce
        else:  # Salgado
            return 30  # Preço da pizza pequena salgada
    elif tamanho == 'M':  # Pizza média
        if sabor == 'PD':
            return 48
        else:
            return 45
    elif tamanho == 'G':  # Pizza grande
        if sabor == 'PD':
            return 66
        else:
            return 60
    return 0  # Valor padrão se nada for válido


# Loop principal para múltiplas pizzas
while True:
    print("\n--- Novo Pedido de Pizza ---")

    # Loop para o primeiro sabor
    while True:
        pedidosabor1 = input('Qual o primeiro sabor deseja? (PS para salgada, PD para doce): ')
        if pedidosabor1 == pizzadoce or pedidosabor1 == pizzasalgada:
            break  # Sabor válido, sai do loop
        else:
            print('Sabor inválido! Tente novamente.')
            continue  # Volta para o início do loop

    # Loop para o segundo sabor
    while True:
        pedidosabor2 = input('Qual o segundo sabor deseja? (PS para salgada, PD para doce): ')
        if pedidosabor2 == pizzadoce or pedidosabor2 == pizzasalgada:
            break
        else:
            print('Sabor inválido! Tente novamente.')
            continue

    # Loop para o tamanho
    while True:
        pedidotamanho = input('Qual tamanho deseja? (P | M | G): ')
        if pedidotamanho == pizzaP or pedidotamanho == pizzaM or pedidotamanho == pizzaG:
            break  # Tamanho válido, sai do loop
        else:
            print('Tamanho inválido! Tente novamente.')
            continue  # Volta para o início do loop

    # Calcular o preço usando a função preco_sabor
    preco_sabor1 = preco_sabor(pedidotamanho, pedidosabor1)  # Chama a função com argumentos
    preco_sabor2 = preco_sabor(pedidotamanho, pedidosabor2)
    preco_pizza = (preco_sabor1 + preco_sabor2)   # Soma dos dois sabores
    total += preco_pizza  # Adiciona ao total acumulado

    # Exibir o pedido e o preço
    print(f'Seu pedido foi uma pizza com sabores {pedidosabor1} e {pedidosabor2} de tamanho {pedidotamanho}.')
    print(f'O preço desta pizza é: R$ {preco_pizza:.2f}')
    print(f'Total acumulado até agora: R$ {total:.2f}')

    # Perguntar se deseja continuar
    S = 'S'
    N = 'N'
    while True:
        continuar = input('Deseja continuar e pedir mais uma pizza? [S/N]: ').upper()
        if continuar == S:
            break  # Continua para o próximo pedido
        elif continuar == N:
            print('Pedido encerrado.')
            break  # Sai do loop de continuação
        else:
            print('Entrada inválida! Digite S ou N.')
            continue  # Volta para o início do loop

    if continuar == N:
        break  # Sai do loop principal

# Exibir o total final fora do loop
print(f'\nO valor total do pedido será de R$ {total:.2f}')
print('Obrigado pela compra!')


