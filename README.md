# DIO-Criando-um-Personal-Trainer-IA-com-Boas-Pr-ticas-de-Prompt-Engineer
Criando um Personal Trainer IA com Boas Práticas de Prompt Engineer

import time

def welcome_message():
    print("\n=== 🏋️ Bem-vindo ao Assistente de Personal Trainer! 🏋️ ===")
    print("Vamos criar um treino personalizado para você!\n")

def get_biotype():
    while True:
        print("\n=== BIOTIPO CORPORAL ===")
        print("1. Ectomorfo - Corpo mais magro, difícil ganhar peso e massa muscular")
        print("2. Mesomorfo - Corpo naturalmente musculoso, facilidade para ganhar massa")
        print("3. Endomorfo - Corpo com tendência a acumular gordura")
        
        try:
            choice = int(input("\nEscolha seu biotipo (1-3): "))
            if choice in [1, 2, 3]:
                return {
                    1: "Ectomorfo",
                    2: "Mesomorfo",
                    3: "Endomorfo"
                }[choice]
        except ValueError:
            pass
        print("❌ Opção inválida! Por favor, escolha 1, 2 ou 3.")

def get_training_days():
    while True:
        print("\n=== DIAS DISPONÍVEIS PARA TREINO ===")
        print("1. 1 dia por semana (Treino Full Body)")
        print("2. 3 dias por semana (Treino ABC)")
        print("3. 5 dias por semana (Treino ABCDE)")
        
        try:
            choice = int(input("\nEscolha a quantidade de dias (1-3): "))
            if choice in [1, 2, 3]:
                return {
                    1: ("Full Body", 1),
                    2: ("ABC", 3),
                    3: ("ABCDE", 5)
                }[choice]
        except ValueError:
            pass
        print("❌ Opção inválida! Por favor, escolha 1, 2 ou 3.")

def get_exercise_type():
    while True:
        print("\n=== TIPO DE EXERCÍCIO ===")
        print("1. Funcional - Exercícios com movimentos naturais")
        print("2. Maquinário - Exercícios em aparelhos")
        print("3. Peso Livre - Exercícios com halteres e barras")
        print("4. Cardio - Exercícios cardiovasculares")
        print("5. HIIT - Treinos intervalados de alta intensidade")
        
        try:
            choice = int(input("\nEscolha o tipo de exercício (1-5): "))
            if choice in [1, 2, 3, 4, 5]:
                return {
                    1: "Funcional",
                    2: "Maquinário",
                    3: "Peso Livre",
                    4: "Cardio",
                    5: "HIIT"
                }[choice]
        except ValueError:
            pass
        print("❌ Opção inválida! Por favor, escolha entre 1 e 5.")

def generate_workout_plan(biotype, training_info, exercise_type):
    training_type, days = training_info
    
    print("\n🏋️ Gerando seu treino personalizado...")
    time.sleep(1)  # Simula processamento
    
    print("\n=== SEU PLANO DE TREINO PERSONALIZADO ===")
    print(f"\n👤 Biotipo: {biotype}")
    print(f"📅 Frequência: {days} dias por semana")
    print(f"💪 Tipo de Treino: {training_type}")
    print(f"🎯 Foco dos exercícios: {exercise_type}\n")
    
    # Recomendações específicas por biotipo
    print("🎯 Recomendações específicas para seu biotipo:")
    if biotype == "Ectomorfo":
        print("- Priorize exercícios compostos com cargas pesadas")
        print("- Faça menos repetições (6-8) com mais séries (4-5)")
        print("- Minimize exercícios cardiovasculares")
        print("- Descanse 2-3 minutos entre as séries")
    elif biotype == "Mesomorfo":
        print("- Balance exercícios compostos e isolados")
        print("- Faça séries moderadas (8-12 repetições)")
        print("- Inclua cardio moderado")
        print("- Descanse 1-2 minutos entre as séries")
    else:  # Endomorfo
        print("- Combine exercícios de força com cardio")
        print("- Faça mais repetições (12-15) com menos descanso")
        print("- Inclua HIIT ou cardio intenso")
        print("- Descanse 30-60 segundos entre as séries")

def main():
    welcome_message()
    biotype = get_biotype()
    training_info = get_training_days()
    exercise_type = get_exercise_type()
    generate_workout_plan(biotype, training_info, exercise_type)
    
    print("\n✨ Deseja mais informações ou tem alguma dúvida? Digite 'S' para sim ou 'N' para não:")
    if input().upper() == 'S':
        print("\n📧 Entre em contato com nosso suporte para mais detalhes sobre seu treino!")
    print("\n🎉 Obrigado por usar nosso Assistente de Personal Trainer! Bom treino! 💪")

if __name__ == "__main__":
    main()
