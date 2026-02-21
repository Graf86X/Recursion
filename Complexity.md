# Complexity


## O(1)
Достъп до елемент по индекс
- Брой на операциите: 1 (Независимо от размера на масивът)
- Взима i-тия елемент

```cpp
int select_element(int arr[], size_t i){
    retrun arr[i];
}
````` 

## O(log n)
Двоично търсене
- Брой на операциите: на всяка стъпка взима по-малко от половината
- Дели масивът на половина
  
````cpp
int binary_search(int* arr, int x, int l, int r){
	if (l > r) return -1;

	int mid = l + (r - l) / 2;
	if (arr[mid] == x) return mid;
	if (arr[mid] > x) return binary_search(arr, x, l, mid - 1);
	if (arr[mid] < x) return binary_search(arr, x, mid + 1, r);
}
````

## O(n)
Линейно търсене
- Брой на операциите: n
- Минава през всички елементи
```cpp
bool find_element(int arr[], size_t n, int elem) {
    for (size_t i = 0; i < n; ++i) {
        if (arr[i] == elem) {
            return true;
        }
    }
    return false;
}
`````

## O(n<sup>2</sup>)

Buble sort
- Брой на операциите: n<sup>2</sup> = n*n
- Два вложени цикъла
````cpp
void Buble_sort(int arr[], size_t n){
    for(size_t i = 0; i < n-1; ++i){
        for(size_t j = 0; j < n - 1 - i; ++j){
            if(arr[j] > arr[j+1])
                swap(arr[j], arr[j+1]);
        }
    }    
}
````

## O(2<sup>n</sup>)
Рекурсивното решение за редицата на Финбуначи
- Брой на операциите: 2<sup>n</sup>
- За n рекурсии има по 2 изхода. Всяко число се разбива на два проблема

````cpp
unsigned int fibunacci(unsigned int n){
    if(n == 0) return 0;
    if(n == 1) return 1;

    return fibunacci(n-1) + fibunacci(n-2);
}
````

## O(n!)
Пермутация без повторение
- Брой на операциите: n!
- Всички възможни подредби, като елементите се ползват точно веднъж
````cpp
void generate_permutations(int* nums, unsigned int pos, const unsigned int n) {
    if (pos == n) {
        return; // не правим нищо
    }

    for (unsigned int i = pos; i < n; ++i) {
        swap(nums[pos], nums[i]);
        generate_permutations(nums, pos + 1, n);
        swap(nums[pos], nums[i]);
    }
}
````
## O(n<sup>n</sup>)
Вариации с повторения
- Брой на операциите: n<sup>n</sup>
- За n позиции имаме n възможности
````cpp
void variation(int* nums, unsigned int pos, const unsigned int n) {
    if (pos == n) {
        return;
    }

    for (unsigned int i = 0; i < n; ++i) {
        swap(nums[pos], nums[i]);
        variation(nums, pos + 1, n);
        swap(nums[pos], nums[i]);
    }
}
````
> Забележка: Разликата меджу кода с времева сложност O(n!) и O(n<sup>n</sup>) е в началната стойност на `i` във *for-цикъла*!
> - O(n!) → `i = pos` (елементите не се повтарят)
> - O(n<sup>n</sup>) → `i = 0` (елементите могат да се повтарят)
