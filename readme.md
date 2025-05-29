*Берет информацию из input:*

    def get_keyword():
        return input("Введите ключевое слово для поиска: ").strip().lower()
*Фильтрует кандидатов по ключевому слову:*

    def filter_candidates(candidates, keyword):
        return [c for c in candidates if keyword in c[3].lower()]
*Выводит результаты поиска:*

    def display_results(matches):
        if not matches:
            print("\nКандидатов не найдено.")
            return
    
        print(f"\nНайдено {len(matches)} подходящих кандидатов:")
    
        for name, age, exp, skills in matches:
            print(f"\nИмя: {name}")
            print(f"Возраст: {age}")
            print(f"Опыт: {exp} лет")
            print(f"Навыки: {skills}")
*Запуск программы:*

    def main():
        candidates = [
            ("Андрей", 24, 3, "Пишу на Python, знаю REST"),
            ("Вадим", 28, 7, "Люблю Go, обожаю REST, могу писать системные утилиты"),
            ("Евгений", 26, 4, "Фанат Python и Rust, люблю писать REST приложения и системные утилиты")]
    
        keyword = get_keyword()
    
        matches = filter_candidates(candidates, keyword)
    
        display_results(matches)

    main()