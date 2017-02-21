---
title: "Compilerfehler C2666 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2666"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2666"
ms.assetid: 78364d15-c6eb-439a-9088-e04a0176692b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2666
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Anzahl Überladungen haben ähnliche Konvertierungen  
  
 Eine überladene Funktion oder ein Operator ist mehrdeutig.   Die formalen Parameterlisten sind für den Compiler möglicherweise zu ähnlich, um die Mehrdeutigkeit auflösen zu können.  Um den Fehler zu beheben, führen Sie für einen oder mehrere der übergebenen Parameter eine explizite Typumwandlung durch.  
  
 Im folgenden Beispiel wird C2666 generiert:  
  
```  
// C2666.cpp  
struct complex {  
   complex(double);  
};  
  
void h(int,complex);  
void h(double, double);  
  
int main() {  
   h(3,4);   // C2666  
}  
```  
  
 Dieser Fehler kann auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben werden:  
  
-   Binäre Operatoren und benutzerdefinierte Konvertierungen zu Zeigertypen  
  
-   Qualifikationskonvertierung und Identitätskonvertierung weichen voneinander ab  
  
 Bei den binären Operatoren \<, \>, \<\=, and \>\= wird ein übergebener Parameter jetzt implizit in den Typ des Operanden konvertiert, wenn der Typ des Parameters ein benutzerdefinierter Konvertierungsoperator definiert, der in den Typ des Operanden konvertiert.  Dies kann jetzt zu Mehrdeutigkeiten führen.  
  
 In Code, der sowohl in der Visual Studio .NET 2003\-Version als auch in der Visual Studio .NET\-Version von Visual C\+\+ gültig ist, rufen Sie den Klassenoperator mithilfe der Funktionssyntax explizit auf.  
  
## Beispiel  
  
```  
// C2666b.cpp  
#include <string.h>  
#include <stdio.h>  
  
struct T   
{  
    T( const T& copy )   
    {  
        m_str = copy.m_str;  
    }  
  
    T( const char* str )   
    {  
        int iSize = (strlen( str )+ 1);  
        m_str = new char[ iSize ];  
        if (m_str)  
            strcpy_s( m_str, iSize, str );  
    }  
  
    bool operator<( const T& RHS )   
    {  
        return m_str < RHS.m_str;  
    }  
  
    operator char*() const   
    {  
        return m_str;  
    }  
  
    char* m_str;  
};  
  
int main()   
{  
    T str1( "ABCD" );  
    const char* str2 = "DEFG";  
  
    // Error – Ambiguous call to operator<()  
    // Trying to convert str1 to char* and then call   
    // operator<( const char*, const char* )?  
    //  OR  
    // trying to convert str2 to T and then call  
    // T::operator<( const T& )?  
  
    if( str1 < str2 )   // C2666  
  
    if ( str1.operator < ( str2 ) )   // Treat str2 as type T  
        printf_s("str1.operator < ( str2 )\n");  
  
    if ( str1.operator char*() < str2 )   // Treat str1 as type char*  
        printf_s("str1.operator char*() < str2\n");  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2666 generiert:  
  
```  
// C2666c.cpp  
// compile with: /c  
  
enum E   
{  
    E_A,   E_B  
};  
  
class A   
{  
    int h(const E e) const {return 0; }  
    int h(const int i) { return 1; }  
    // Uncomment the following line to resolve.  
    // int h(const E e) { return 0; }  
  
    void Test()   
    {  
        h(E_A);   // C2666  
        h((const int) E_A);  
        h((int) E_A);  
    }  
};  
```