--------------------------------------------------------------------------------------
#Bloco 1#
def calcular_tmb(peso, idade, sexo):
    """Calcula a Taxa Metabólica Basal (TMB) usando a fórmula de Harris-Benedict."""
    if sexo.lower() == 'masculino':
        tmb = 88.36 + (13.4 * peso) + (4.8 * 0) - (5.7 * idade)
    elif sexo.lower() == 'feminino':
        tmb = 447.6 + (9.2 * peso) + (3.1 * 0) - (4.3 * idade)
    else:
        raise ValueError("Sexo deve ser 'masculino' ou 'feminino'.")
    return tmb
-----------------------------------------------------------------------------------
#Bloco 2#
    def obter_calorias_por_minuto(exercicio):
    """Retorna a quantidade de calorias queimadas por minuto para um exercício dado."""
    exercicios = {
        "Andando de bicicleta": 4,
        "Balé": 8,
        "Basquete": 10,
        "Beijando": 8 / 60,  # Convertido para calorias por minuto
        "Boxe": 11,
        "Caminhada": 5.5,
        "Capoeira": 12,
        "Ciclismo": 6,
        "Corrida": 10,
        "Dança de Salão": 3.5,
        "Esqui aquático": 11,
        "Esqui na neve": 7.5,
        "Futebol": 9,
        "Ginástica aeróbica": 6,
        "Ginástica olímpica": 6,
        "Golfe": 3,
        "Handebol": 10,
        "Hidroginástica": 6,
        "Jiu-jitsu": 12,
        "Judô": 12,
        "Mountain bike": 12,
        "Musculação": 5,
        "Natação": 9,
        "Remo": 11,
        "Squash": 13,
        "Surfe": 8,
        "Tênis": 8,
        "Vôlei": 6,
    }

    if exercicio in exercicios:
        return exercicios[exercicio]
    else:
        raise ValueError("Exercício não encontrado na tabela.")
-----------------------------------------------------------------------------------------------------------
#Bloco 3#
        def calcular_tempo_exercicio(calorias_ingeridas, calorias_por_minuto, tmb):
    """Calcula o tempo necessário para queimar as calorias ingeridas."""
    # Ajusta as calorias por minuto com base na TMB
    calorias_por_minuto_ajustadas = calorias_por_minuto * (tmb / 2000)  # Ajuste hipotético
    return calorias_ingeridas / calorias_por_minuto_ajustadas
------------------------------------------------------------------------------------------------------
#Bloco 4#
    def main():
    # Solicita ao usuário os dados pessoais
    idade = int(input("Digite sua idade: "))
    peso = float(input("Digite seu peso em kg: "))
    sexo = input("Digite seu sexo (masculino/feminino): ").strip()

    # Calcula a TMB
    tmb = calcular_tmb(peso, idade, sexo)

    # Solicita ao usuário o tipo de exercício
    exercicio = input("Digite o tipo de exercício: ").strip()

    # Solicita a quantidade de calorias ingeridas
    calorias_ingeridas = float(input("Digite a quantidade de calorias ingeridas: "))

    try:
        # Obtém a quantidade de calorias queimadas por minuto para o exercício escolhido
        calorias_por_minuto = obter_calorias_por_minuto(exercicio)

        # Calcula o tempo necessário de exercício
        tempo_necessario = calcular_tempo_exercicio(calorias_ingeridas, calorias_por_minuto, tmb)

        # Exibe o resultado
        print(f"Você precisa fazer {tempo_necessario:.2f} minutos de {exercicio} para queimar {calorias_ingeridas} calorias.")
    except ValueError as e:
        print(e)

if __name__ == "__main__":
    main()
