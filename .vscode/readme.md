import random

def play_game():
    print("=== Привет! Я загадал число от 1 до 100. Попробуй отгадать! ===")
    secret_number = random.randint(1, 100)
    attempts = 0

    while True:
        user_input = input("Введите ваше число (или 'стоп' для выхода): ")
        
        if user_input.lower() == 'стоп':
            print(f"Жаль! Я загадал число: {secret_number}")
            break

        if not user_input.isdigit():
            print("Пожалуйста, введите целое число!")
            continue

        guess = int(user_input)
        attempts += 1

        if guess < secret_number:
            print("Мое число БОЛЬШЕ 🔼")
        elif guess > secret_number:
            print("Мое число МЕНЬШЕ 🔽")
        else:
            print(f"🎉 Поздравляю! Вы угадали число {secret_number} за {attempts} попыток!")
            break

if __name__ == "__main__":
    play_game()
    