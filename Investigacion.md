# Investigación sobre Métodos de Ordenamiento

## Introducción

Los métodos de ordenamiento son algoritmos utilizados para organizar elementos en un conjunto de datos de manera ascendente o descendente. En este documento, se explorarán tres métodos de ordenamiento clásicos: Bubble Sort, Selection Sort, e Insertion Sort. Cada uno de estos algoritmos tiene sus propias características y eficiencia en diferentes situaciones.

## 1. Bubble Sort

### Descripción:

Bubble Sort es un sencillo algoritmo de ordenamiento que compara repetidamente pares de elementos adyacentes y los intercambia si están en el orden incorrecto. Este proceso se repite hasta que no se necesitan más intercambios, lo que indica que el conjunto de datos está ordenado.

### Código en C++:

```cpp
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                // Intercambiar elementos si están en el orden incorrecto
                swap(arr[j], arr[j+1]);
            }
        }
    }
}
```

## 2. Selection Sort

### Descripción:

Selection Sort divide la lista en dos partes: la sublista ordenada, que se construye de izquierda a derecha, y la sublista no ordenada, que contiene los elementos restantes. En cada iteración, el algoritmo busca el elemento mínimo de la sublista no ordenada y lo intercambia con el primer elemento de esa sublista.

### Código en C++:

```cpp
void selectionSort(int arr[], int n) {
    int i, j, minIndex;
    for (i = 0; i < n-1; i++) {
        minIndex = i;
        for (j = i+1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        // Intercambiar el elemento mínimo con el primer elemento no ordenado
        swap(arr[minIndex], arr[i]);
    }
}
```

## 3. Insertion Sort

### Descripción:

Insertion Sort construye una sublista ordenada uno a la vez tomando elementos de la lista y colocándolos en la posición correcta. En cada iteración, el algoritmo toma un elemento de la sublista no ordenada y lo inserta en su lugar correcto dentro de la sublista ordenada.

### Código en C++:

```cpp
void insertionSort(int arr[], int n) {
    int i, key, j;
    for (i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;
        // Mover elementos de la sublista ordenada que son mayores que 'key'
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}
```

## Conclusiones

Cada uno de estos métodos de ordenamiento tiene sus ventajas y desventajas en términos de eficiencia y aplicabilidad. La elección del algoritmo depende del tamaño del conjunto de datos, la disposición inicial de los elementos y los recursos disponibles. Es importante entender las características de cada método para seleccionar el más adecuado para un caso particular.
