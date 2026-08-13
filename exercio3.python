def calcular_tempo_atendimento(itens):
    return 2 + (0.5 * itens)

def encontrar_caixa_menor_tempo(tempos_caixas):
    # Encontra o índice do caixa com o menor tempo. 
    # Em caso de empate, o index() já retorna o menor índice.
    menor_tempo = min(tempos_caixas)
    return tempos_caixas.index(menor_tempo)

def alocar_cliente(caixas, tempos_caixas, cliente_codigo, tempo):
    idx_caixa = encontrar_caixa_menor_tempo(tempos_caixas)
    caixas[idx_caixa].append(cliente_codigo)
    tempos_caixas[idx_caixa] += tempo

def calcular_estatisticas(tempos_caixas, total_clientes):
    tempo_medio = sum(tempos_caixas) / total_clientes if total_clientes > 0 else 0
    maior_tempo = max(tempos_caixas)
    caixa_maior = tempos_caixas.index(maior_tempo) + 1
    
    menor_tempo = min(tempos_caixas)
    caixa_menor = tempos_caixas.index(menor_tempo) + 1
    
    return tempo_medio, caixa_maior, caixa_menor, maior_tempo

def exibir_resultado(caixas, tempos_caixas, estatisticas):
    tempo_medio, caixa_maior, caixa_menor, tempo_total = estatisticas
    
    print("\n=== RESULTADO DA SIMULAÇÃO ===")
    for i in range(len(caixas)):
        clientes = ", ".join(caixas[i]) if caixas[i] else "Nenhum"
        print(f"Caixa {i+1}:")
        print(f"  Clientes atendidos: {clientes}")
        print(f"  Tempo total: {tempos_caixas[i]:.2f} minutos\n")
        
    print(f"Tempo médio de atendimento por cliente: {tempo_medio:.2f} minutos")
    print(f"Caixa com maior tempo acumulado: Caixa {caixa_maior}")
    print(f"Caixa com menor tempo acumulado: Caixa {caixa_menor}")
    print(f"Tempo total necessário para encerrar os atendimentos: {tempo_total:.2f} minutos")

def main():
    while True:
        qtd_caixas = int(input("Quantidade de caixas disponíveis: "))
        if qtd_caixas > 0: break
        print("A quantidade de caixas deve ser maior que zero.")

    while True:
        qtd_clientes = int(input("Quantidade de clientes a serem atendidos: "))
        if qtd_clientes > 0: break
        print("A quantidade de clientes deve ser maior que zero.")

    caixas = [[] for _ in range(qtd_caixas)]
    tempos_caixas = [0.0] * qtd_caixas
    
    print("\n--- Entrada de Clientes ---")
    for i in range(qtd_clientes):
        print(f"Cliente {i+1}:")
        codigo = input("  Código: ")
        while True:
            itens = int(input("  Quantidade de itens: "))
            if itens >= 0: break
            print("  Erro: A quantidade de itens não pode ser negativa.")
            
        tempo = calcular_tempo_atendimento(itens)
        alocar_cliente(caixas, tempos_caixas, codigo, tempo)

    estatisticas = calcular_estatisticas(tempos_caixas, qtd_clientes)
    exibir_resultado(caixas, tempos_caixas, estatisticas)

if __name__ == "__main__":
    main()