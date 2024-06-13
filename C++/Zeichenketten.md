```cpp
#include <codecvt>  
#include <iostream>  
#include <string>  
int main()  
{  
    const char* name = "Carsten";  
    std::cout << name << std::endl;  
    // name[0] = 'K'; geht nicht!!!  
    // delete(name); Faustregel ohne new kein delete  
    char name1[] = {'C','a','r','s','t','e','n','\0'};  
    //Stringterminator \0 setzen oder nur 0  
    // Wert ist im Stack    // name1[0] = 'K';    std::cout << name1 << std::endl;  
  
    const wchar_t* name2 = L"Biermann"; // je nach System 16 oder 32 Bit groß  
    std::wcout << name2 << std::endl;  
  
    // const char16_t* name3 = u"Carsten"; // 16Bit groß  
    // std::wstring_convert<std::codecvt_utf8_utf16<char16_t>, char16_t> convert;    // std::string str = convert.to_bytes(name3);    // std::cout << str << std::endl;  
    // const char32_t* name4 = U"Carsten"; // 32Bit groß    // std::wstring_convert<std::codecvt_utf8<char32_t>, char32_t> convert;    // std::string str = convert.to_bytes(name4);    // std::cout << str << std::endl;  
    std::string name5 = "Carsten";  
    std::cout << name5 << std::endl;  
  
    std::string name6 = "Hallo ";  
    //std::string name7 = "Hallo " + "Welt!"; geht nicht, weil zwei Pointer addiert werden  
    std::string name7 = name6 + "Welt!";  
    std::cout << name7 << std::endl;  
  
    std::wstring name8 = L"Hallo";  
    std::u16string name9 = u" zwei";  
    std::u32string name10 = U"Welt";  
  
    const char* mehrzeiliger_text = R"(Ein Zeilenumbruch geht in C normalerweise mit \n,  
    aber hier wird das ignoriert. Viel einfacher ist dies mit einem RAW String.    Da kann man sogar "Hochkommata" verwenden)";  
    std::cout << mehrzeiliger_text << std::endl;  
    return 0;  
}
```

