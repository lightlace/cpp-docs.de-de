---
title: Benutzerdefinierte Literale (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a461f4ca384585008ccf47fa2bfda91d36e724ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-literals--c"></a>Benutzerdefinierte Literale (C++)
Es gibt fünf Hauptkategorien von Literalen: Integer, Zeichendaten, Gleitkommazahlen, Zeichenfolge, boolescher Wert und Zeiger.  Ab C++ 11 können Sie eigene Literale basierend auf diesen Kategorien definieren, um syntaktische Verknüpfungen für allgemeine Idiome und eine höhere Typsicherheit bereitzustellen. Beispielsweise angenommen, Sie verfügen über eine Distanz-Klasse. Sie könnten ein Literal für Kilometer und ein anderes für Meilen definieren und den Benutzern empfehlen, die Maßeinheiten explizit anzugeben: Auto d = 42.0_km oder Auto d = 42.0_mi. Es gibt keine Leistungsvorteile oder Nachteile durch benutzerdefinierte Literale. Sie werden in erster Linie zur Vereinfachung oder für die Typableitung bei der Kompilierung genutzt. Die Standardbibliothek hat benutzerdefinierte Literale für Std: String, Std:: Complex und Einheiten in der Zeit und Dauer von Vorgängen in der \<Chrono >-Header:  
  
```  
Distance d = 36.0_mi + 42.0_km;         // Custom UDL (see below)  
    std::string str = "hello"s + "World"s;  // Standard Library <string> UDL  
    complex<double> num =   
        (2.0 + 3.01i) * (5.0 + 4.3i);       // Standard Library <complex> UDL  
    auto duration = 15ms + 42h;             // Standard Library <chrono> UDLs  
```  
  
## <a name="user-defined-literal-operator-signatures"></a>Benutzerdefinierte Literaloperatorsignaturen  
 Sie implementieren ein benutzerdefiniertes Literal durch Definieren von `operator""` im Namespacebereich mit einem der folgenden Formate:  
  
```  
ReturnType operator "" _a(unsigned long long int);   // Literal operator for user-defined INTEGRAL literal  
ReturnType operator "" _b(long double);              // Literal operator for user-defined FLOATING literal  
ReturnType operator "" _c(char);                     // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _d(wchar_t);                  // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _e(char16_t);                 // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _f(char32_t);                 // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _g(const     char*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _h(const  wchar_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _i(const char16_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _g(const char32_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _r(const char*);              // Raw literal operator  
template<char...> ReturnType operator "" _t();       // Literal operator template  
```  
  
 Die Operatornamen im vorherigen Beispiel sind Platzhalter für die von Ihnen bereitgestellten Namen. Der führende Unterstrich ist jedoch erforderlich. (Nur die Standardbibliothek darf Literale ohne Unterstrich definieren.) Im Rückgabetyp passen Sie die Konvertierung oder einen anderen Vorgang an, der vom Literal ausgeführt wird. Alle diese Operatoren können auch `constexpr` definiert werden.  
  
## <a name="cooked-literals"></a>Verarbeitete Literale  
 Im Quellcode ist jedes Literal, ob benutzerdefiniert oder nicht, im Grunde eine Sequenz von alphanumerischen Zeichen, z. B. `101` oder `54.7` oder `"hello"` oder `true`. Der Compiler interpretiert die Sequenz eine ganze Zahl, "Float" const Char\* Zeichenfolge ein, und So weiter. Ein benutzerdefiniertes Literal, das als Eingabe akzeptiert, was geben, dass den Compiler dem Literalwert zugewiesen wird informell als bezeichnet eine *verarbeitete Literal*. Alle ober aufgeführten Operatoren außer `_r` und `_t` sind verarbeitete Literale. Beispielsweise würde ein Literal `42.0_km` an einen Operator mit dem Namen _km gebunden, der eine Signatur ähnlich _b hat, und das Literal `42_km` an einen Operator mit einer Signatur ähnlich _a gebunden.  
  
 Das folgende Beispiel zeigt, wie benutzerdefinierte Literale Aufrufer zu einer expliziten Eingabe auffordern können. Zum Erstellen der `Distance` muss der Benutzer explizit Kilometer oder Meilen mit den entsprechenden benutzerdefinierten Literalzeichen angeben. Natürlich können Sie das gleiche Ergebnis auch auf andere Weise erreichen, aber benutzerdefinierte Literale sind weniger aufwändig als die Alternativen.  
  
```  
struct Distance  
{  
private:  
    explicit Distance(long double val) : kilometers(val)  
    {}  
  
    friend Distance operator"" _km(long double  val);  
    friend Distance operator"" _mi(long double val);  
    long double kilometers{ 0 };  
public:  
    long double get_kilometers() { return kilometers; }  
    Distance operator+(Distance& other)  
    {  
        return Distance(get_kilometers() + other.get_kilometers());  
    }  
};  
  
Distance operator"" _km(long double  val)  
{  
    return Distance(val);  
}  
  
Distance operator"" _mi(long double val)  
{  
    return Distance(val * 1.6);  
}  
int main(int argc, char* argv[])  
{  
    // Must have a decimal point to bind to the operator we defined!  
    Distance d{ 402.0_km }; // construct using kilometers  
    cout << "Kilometers in d: " << d.get_kilometers() << endl; // 402  
  
    Distance d2{ 402.0_mi }; // construct using miles  
    cout << "Kilometers in d2: " << d2.get_kilometers() << endl;  //643.2  
  
    // add distances constructed with different units  
    Distance d3 = 36.0_mi + 42.0_km;  
    cout << "d3 value = " << d3.get_kilometers() << endl; // 99.6  
  
   // Distance d4(90.0); // error constructor not accessible  
  
    string s;  
    getline(cin, s);  
    return 0;  
}  
```  
  
 Beachten Sie, dass die Literalzahl eine Dezimalstelle enthalten muss, da andernfalls die Zahl als Ganzzahl interpretiert werden würde, was mit dem Operator nicht kompatibel wäre. Beachten Sie außerdem, dass bei der Eingabe von Gleitkommazahlen der Typ `long double` und bei Ganzzahlen `long long` sein muss.  
  
## <a name="raw-literals"></a>Unformatierte Literale  
 Bei unformatierten benutzerdefinierte Literalen akzeptiert der von Ihnen definierte Operator das Literal als Sequenz von Char-Werten. Es liegt bei Ihnen diese Sequenz als eine Zahl, Zeichenfolge oder einen anderen Typ zu interpretieren. Aus der zuvor auf dieser Seite aufgeführten Liste von Operatoren können `_r` und `_t` zum Definieren von unformatierten Literalen verwendet werden:  
  
```  
ReturnType operator "" _r(const char*);              // Raw literal operator  
template<char...> ReturnType operator "" _t();       // Literal operator template  
```  
  
 Sie können mit unformatierten Literalen eine benutzerdefinierte Interpretation einer Eingabesequenz bereitzustellen, die sich von der Ausführung durch den Compiler unterscheidet. Sie könnten beispielsweise ein Literal definieren, das die Sequenz `4.75987` in einen benutzerdefinierten Dezimaltyp anstatt in einen IEEE 754-Gleitkommatyp konvertiert. Unformatierte Literale können wie verarbeitete Literale auch zur Validierung von Eingabesequenzen zur Kompilierzeit verwendet werden.  
  
### <a name="example"></a>Beispiel  
  
### <a name="limitations-of-raw-literals"></a>Einschränkungen von unformatierten Literalen  
 Der unformatierte Literaloperator und die Vorlage für den Literaloperator funktionieren nur für Ganzzahl- und Gleitkommatypen benutzerdefinierter Literale, wie im folgenden Beispiel gezeigt:  
  
```  
#include <cstddef>  
#include <cstdio>  
  
void operator "" _dump(unsigned long long int lit)  { printf("operator \"\" _dump(unsigned long long int) : ===>%llu<===\n", lit); };  // Literal operator for user-defined INTEGRAL literal  
void operator "" _dump(long double lit)             { printf("operator \"\" _dump(long double)            : ===>%Lf<===\n",  lit); };  // Literal operator for user-defined FLOATING literal  
void operator "" _dump(char lit)                    { printf("operator \"\" _dump(char)                   : ===>%c<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(wchar_t lit)                 { printf("operator \"\" _dump(wchar_t)                : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(char16_t lit)                { printf("operator \"\" _dump(char16_t)               : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(char32_t lit)                { printf("operator \"\" _dump(char32_t)               : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(const     char* lit, size_t) { printf("operator \"\" _dump(const     char*, size_t): ===>%s<===\n",   lit); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const  wchar_t* lit, size_t) { printf("operator \"\" _dump(const  wchar_t*, size_t): ===>%ls<===\n",  lit); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const char16_t* lit, size_t) { printf("operator \"\" _dump(const char16_t*, size_t):\n"                  ); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const char32_t* lit, size_t) { printf("operator \"\" _dump(const char32_t*, size_t):\n"                  ); };  // Literal operator for user-defined STRING literal  
void operator "" _dump_raw(const char* lit)         { printf("operator \"\" _dump_raw(const char*)        : ===>%s<===\n",   lit); };  // Raw literal operator  
  
template<char...> void operator "" _dump_template();       // Literal operator template  
  
int main(int argc, const char* argv[])  
{  
    42_dump;  
    3.1415926_dump;  
    3.14e+25_dump;  
     'A'_dump;  
    L'B'_dump;  
    u'C'_dump;  
    U'D'_dump;  
      "Hello World"_dump;  
     L"Wide String"_dump;  
    u8"UTF-8 String"_dump;  
     u"UTF-16 String"_dump;  
     U"UTF-32 String"_dump;  
  
    42_dump_raw;  
    3.1415926_dump_raw;  
    3.14e+25_dump_raw;  
    // 'A'_dump_raw;               // There is no raw literal operator or literal operator template support on this type  
    //L'B'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //u'C'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //U'D'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //  "Hello World"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    // L"Wide String"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    //u8"UTF-8 String"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    // u"UTF-16 String"_dump_raw;  // There is no raw literal operator or literal operator template support on this type  
    // U"UTF-32 String"_dump_raw;  // There is no raw literal operator or literal operator template support on this type  
}  
/*****  
Output:  
operator "" _dump(unsigned long long int) : ===>42<===  
operator "" _dump(long double)            : ===>3.141593<===  
operator "" _dump(long double)            : ===>31399999999999998506827776.000000<===  
operator "" _dump(char)                   : ===>A<===  
operator "" _dump(wchar_t)                : ===>66<===  
operator "" _dump(char16_t)               : ===>67<===  
operator "" _dump(char32_t)               : ===>68<===  
operator "" _dump(const     char*, size_t): ===>Hello World<===  
operator "" _dump(const  wchar_t*, size_t): ===>Wide String<===  
operator "" _dump(const     char*, size_t): ===>UTF-8 String<===  
operator "" _dump(const char16_t*, size_t):  
operator "" _dump(const char32_t*, size_t):  
operator "" _dump_raw(const char*)        : ===>42<===  
operator "" _dump_raw(const char*)        : ===>3.1415926<===  
operator "" _dump_raw(const char*)        : ===>3.14e+25<===   
*****/  
  
```