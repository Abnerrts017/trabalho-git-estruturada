def cadastrar_produtos():
    produtos = []
    while True:
        try:
            n = int(input("Digite a quantidade de produtos que serão cadastrados: "))
            if n > 0:
                break
            print("A quantidade deve ser maior que zero.")
        except ValueError:
            print("Entrada inválida. Digite um número inteiro.")

    for i in range(n):
        print(f"\n--- Cadastro do Produto {i+1} ---")
        nome = input("Nome do produto: ")
        qtd = int(input("Quantidade inicial em estoque: "))
        preco = float(input("Preço unitário: R$ "))
        produtos.append({"nome": nome, "qtd": qtd, "preco": preco})
    
    return produtos

def buscar_produto(produtos, nome_busca):
    for produto in produtos:
        if produto["nome"].lower() == nome_busca.lower():
            return produto
    return None

def adicionar_estoque(produtos):
    nome = input("Digite o nome do produto para adicionar estoque: ")
    produto = buscar_produto(produtos, nome)
    if produto:
        qtd = int(input("Quantidade a adicionar: "))
        if qtd > 0:
            produto["qtd"] += qtd
            print("Estoque atualizado com sucesso!")
        else:
            print("Quantidade deve ser positiva.")
    else:
        print("Produto não encontrado.")

def retirar_estoque(produtos):
    nome = input("Digite o nome do produto para retirar do estoque: ")
    produto = buscar_produto(produtos, nome)
    if produto:
        qtd = int(input("Quantidade a retirar: "))
        if qtd > 0:
            if produto["qtd"] >= qtd:
                produto["qtd"] -= qtd
                print("Retirada realizada com sucesso!")
            else:
                print("Erro: Estoque insuficiente.")
        else:
            print("Quantidade deve ser positiva.")
    else:
        print("Produto não encontrado.")

def consultar_produto(produtos):
    nome = input("Digite o nome do produto para consulta: ")
    produto = buscar_produto(produtos, nome)
    if produto:
        print(f"\nProduto: {produto['nome']} | Estoque: {produto['qtd']} | Preço: R$ {produto['preco']:.2f}")
    else:
        print("Produto não encontrado.")

def listar_produtos(produtos):
    print("\n--- Lista de Produtos em Estoque ---")
    for prod in produtos:
        valor_total = prod["qtd"] * prod["preco"]
        print(f"Nome: {prod['nome']} | Qtd: {prod['qtd']} | Preço: R$ {prod['preco']:.2f} | Valor Total: R$ {valor_total:.2f}")

def menu():
    produtos = cadastrar_produtos()
    
    while True:
        print("\n=== MENU DE ESTOQUE ===")
        print("(a) Adicionar unidades ao estoque")
        print("(b) Retirar unidades do estoque")
        print("(c) Consultar um produto")
        print("(d) Listar todos os produtos")
        print("(e) Encerrar o programa")
        
        opcao = input("Escolha uma opção: ").lower()
        
        if opcao == 'a':
            adicionar_estoque(produtos)
        elif opcao == 'b':
            retirar_estoque(produtos)
        elif opcao == 'c':
            consultar_produto(produtos)
        elif opcao == 'd':
            listar_produtos(produtos)
        elif opcao == 'e':
            print("Encerrando o programa...")
            break
        else:
            print("Opção inválida. Tente novamente.")

if __name__ == "__main__":
    menu()