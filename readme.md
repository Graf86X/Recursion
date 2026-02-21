# Complexity


## O(1)
Достъп до елемент

```cpp
int select_element(int arr[], unsigned int i){
    retrun arr[i];
}
````` 

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

## O(2<sup>n</sup>)
Рекурсивното решение за редицата на Финбуначи

````cpp
unsigned int fibunacci(unsigned int n){
    if(n == 0) return 0;
    if(n == 1) return 1;

    return fibunacci(n-1) + fibunacci(n-2);
}
````
