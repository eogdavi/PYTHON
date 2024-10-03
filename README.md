# Função para calcular a média e determinar a situação do aluno
def calcular_situacao():
    # Solicita o nome do aluno
    nome = input("Digite o nome do aluno: ")

    # Lista para armazenar as notas
    notas = []
    
    # Coletando as 4 notas
    for i in range(1, 5):
        nota = float(input(f"Digite a {i}ª nota do aluno (0 a 10): "))
        while nota < 0 or nota > 10:
            print("Nota inválida. Digite uma nota entre 0 e 10.")
            nota = float(input(f"Digite a {i}ª nota do aluno (0 a 10): "))
        notas.append(nota)

    # Calcula a média das notas
    media = sum(notas) / len(notas)

    # Verifica a situação do aluno
    if media < 3:
        situacao = "Reprovado"
    elif 3 <= media <= 6:
        situacao = "Recuperação"
    else:
        situacao = "Aprovado"

    # Exibe o resultado
    print(f"O aluno {nome} ficou com média {media:.2f} e está {situacao}.")

# Chama a função
calcular_situacao()
