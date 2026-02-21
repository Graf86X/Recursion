# Complexity


## O(1)
Достъп до елемент

```cpp
int select_element(int arr[], size_t i){
    retrun arr[i];
}
````` 

## O(log n)
Двоично търсене
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

````cpp
unsigned int fibunacci(unsigned int n){
    if(n == 0) return 0;
    if(n == 1) return 1;

    return fibunacci(n-1) + fibunacci(n-2);
}
````
