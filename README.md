# rep1
def analyze_matrix(matrix):
    """
    Анализирует матрицу и возвращает номера строк,
    в которых количество положительных элементов больше, чем отрицательных.
    """
    result = []
    for i, row in enumerate(matrix):
        positive_count = sum(1 for elem in row if elem > 0)
        negative_count = sum(1 for elem in row if elem < 0)
        if positive_count > negative_count:
            result.append(i + 1)  # +1 для нумерации строк с 1, а не с 0
    return result

def main():
    # Ввод размеров матрицы
    n = int(input("Введите количество строк (n): "))
    m = int(input("Введите количество столбцов (m): "))

    # Ввод элементов матрицы
    matrix = []
    print("Введите элементы матрицы построчно:")
    for i in range(n):
        row = list(map(float, input(f"Строка {i + 1}: ").split()))
        if len(row) != m:
            print(f"Ошибка: в строке должно быть {m} элементов.")
            return
        matrix.append(row)

    # Анализ матрицы
    result = analyze_matrix(matrix)

    # Вывод результатов
    if result:
        print("Номера строк, содержащих больше положительных элементов, чем отрицательных:")
        print(", ".join(map(str, result)))
    else:
        print("Нет строк, содержащих больше положительных элементов, чем отрицательных.")

if __name__ == "__main__":
    main()
