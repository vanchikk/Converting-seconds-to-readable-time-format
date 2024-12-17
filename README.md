# Converting-seconds-to-readable-time-format

seconds_input = int(input("Введіть кількість секунд (0-8639999): "))

if 0 <= seconds_input < 8640000:
    days, remaining_seconds = divmod(seconds_input, 86400)
    hours, remaining_seconds = divmod(remaining_seconds, 3600)
    minutes, seconds = divmod(remaining_seconds, 60)

    if days % 10 == 1 and days % 100 != 11:
        day_word = "день"
    elif 2 <= days % 10 <= 4 and not (12 <= days % 100 <= 14):
        day_word = "дні"
    else:
        day_word = "днів"

    print(f"{days} {day_word}, {str(hours).zfill(2)}:{str(minutes).zfill(2)}:{str(seconds).zfill(2)}")
else:
    print("Некоректний ввід. Число повинно бути від 0 до 8639999.")
