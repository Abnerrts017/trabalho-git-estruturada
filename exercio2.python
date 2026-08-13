def calcular_media(n1, n2, n3):
    return (n1 + n2 + n3) / 3

def classificar_situacao(media):
    if media >= 7:
        return "Aprovado"
    elif 5 <= media < 7:
        return "Recuperação"
    else:
        return "Reprovado"

def ler_dados_alunos():
    alunos = []
    n = int(input("Digite a quantidade de alunos na turma: "))
    
    for i in range(n):
        print(f"\n--- Aluno {i+1} ---")
        nome = input("Nome: ")
        n1 = float(input("Nota 1: "))
        n2 = float(input("Nota 2: "))
        n3 = float(input("Nota 3: "))
        
        media = calcular_media(n1, n2, n3)
        situacao = classificar_situacao(media)
        
        alunos.append({
            "nome": nome,
            "n1": n1,
            "n2": n2,
            "n3": n3,
            "media": media,
            "situacao": situacao
        })
    return alunos

def exibir_relatorio(alunos):
    if not alunos:
        return

    print("\n--- Tabela Final de Notas ---")
    print(f"{'Nome':<15} | {'N1':<5} | {'N2':<5} | {'N3':<5} | {'Média':<6} | {'Situação'}")
    print("-" * 65)
    
    soma_medias = 0
    maior_media = alunos[0]
    menor_media = alunos[0]
    aprovados = rec = reprovados = 0
    
    for aluno in alunos:
        print(f"{aluno['nome']:<15} | {aluno['n1']:<5.1f} | {aluno['n2']:<5.1f} | {aluno['n3']:<5.1f} | {aluno['media']:<6.2f} | {aluno['situacao']}")
        
        soma_medias += aluno['media']
        
        if aluno['media'] > maior_media['media']:
            maior_media = aluno
        if aluno['media'] < menor_media['media']:
            menor_media = aluno
            
        if aluno['situacao'] == "Aprovado":
            aprovados += 1
        elif aluno['situacao'] == "Recuperação":
            rec += 1
        else:
            reprovados += 1
            
    media_geral = soma_medias / len(alunos)
    
    print("\n--- Estatísticas da Turma ---")
    print(f"Média geral da turma: {media_geral:.2f}")
    print(f"Aluno com maior média: {maior_media['nome']} ({maior_media['media']:.2f})")
    print(f"Aluno com menor média: {menor_media['nome']} ({menor_media['media']:.2f})")
    print(f"Quantidade de aprovados: {aprovados}")
    print(f"Quantidade em recuperação: {rec}")
    print(f"Quantidade de reprovados: {reprovados}")

if __name__ == "__main__":
    lista_alunos = ler_dados_alunos()
    exibir_relatorio(lista_alunos)