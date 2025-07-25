## Название алгоритма – Быстрая сортировка (Quick Sort)

**Описание алгоритма** – быстрая сортировка — это "разделяй и властвуй" алгоритм. Выбирается опорный элемент (pivot), и массив разбивается на элементы меньше и больше него, после чего рекурсивно сортируются части.

**Особенности:**

- Очень эффективна на практике

- Неустойчивая

**Реализация алгоритма**
```java
import java.util.*;
import java.lang.*;
import java.io.*;

class QuickSort {
    public static void sort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            sort(arr, low, pi - 1);
            sort(arr, pi + 1, high);
        }
    }

    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (arr[j] <= pivot) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return i + 1;
    }
}

class Main {
    public static void main(String[] args) {
        int[] arr = {5, 2, 9, 1, 5, 6};
        QuickSort.sort(arr, 0, arr.length - 1);

        // Print the sorted array
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }
}
```
#### Алгоритмическая сложность алгоритма 

- Лучший случай: O(n log n)

- Средний случай: O(n log n)

- Худший случай: O(n²)
