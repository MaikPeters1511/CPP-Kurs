```cpp
#include <iostream>  
  
int main() {  
    const int big = 10;  
    int field[big];  
  
    // Initialieren von field bei der Laufzeit erst  
    for (int i = 0; i < big; ++i)  
    {  
        field[i] = i * 10;  
        std::cout << field[i] << " ";  
    }  
    std::cout << std::endl;  
  
    // \0 ist der Textterminator was das Ende des Strings darstellt  
    char text[] = {'H','a','l','l','o','\0'};  
    std::cout << text << std::endl;  
  
    int size = 0;  
    std::cout << "Geben sie an wieviele Zahlen eingelesen werden soll?";  
    std::cin >> size;  
  
    int* zahlen = new int[size];  
    if (zahlen == nullptr)  
    {  
        std::cerr << "Memory allocation failed\n";  
        exit(1);    }  
    else  
    {  
        for (int i = 0; i < size; ++i)  
        {  
            std::cout << i + 1 << ". Zahl:";  
            std::cin >> zahlen[i];  
        }  
    }  
  
    std::cout << std::endl;  
    delete[] zahlen;  
  
    return 0;  
}
```