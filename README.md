def sum_negatives_between_min_max(arr):
    """
    Находит сумму отрицательных элементов, расположенных между максимальным и минимальным элементами массива.
    Если между ними нет отрицательных элементов, возвращает 0.
    """
    if len(arr) <= 1:
        return 0

    # Находим индексы максимального и минимального элементов
    max_idx = arr.index(max(arr))
    min_idx = arr.index(min(arr))

    # Определяем границы диапазона: от меньшего индекса к большему
    start = min(max_idx, min_idx) + 1
    end = max(max_idx, min_idx)

    # Если между min и max нет элементов (они соседние), возвращаем 0
    if start >= end:
        return 0

    # Суммируем отрицательные элементы в найденном диапазоне
    negative_sum = sum(x for x in arr[start:end] if x < 0)

    return negative_sum


# Пример использования
if __name__ == "__main__":
    # Тестовый массив
    A = [3, -2, 5, -1, -4, 8, -3, 1]
    result = sum_negatives_between_min_max(A)
    print(f"Массив: {A}")
    print(f"Сумма отрицательных элементов между min и max: {result}")
