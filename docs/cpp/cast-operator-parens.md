---
title: "Umwandlungsoperator: ()"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "()-Umwandlungsoperator"
  - "Umwandlungsoperatoren"
ms.assetid: 4c99eb92-1b19-4a5d-9840-5d8c29b8453e
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Umwandlungsoperator: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Typumwandlung stellt eine Möglichkeit zum expliziten Konvertieren des Typs eines Objekts in einer bestimmten Situation bereit.  
  
## Syntax  
  
```  
  
      unary-expression  
( type-name ) cast-expression  
```  
  
## Hinweise  
 Jeder unäre Ausdruck wird als Umwandlungsausdruck betrachtet.  
  
 Der Compiler behandelt *cast\-expression* als *type\-name*\-Typ, nachdem eine Typumwandlung vorgenommen wurde.  Umwandlungen können verwendet werden, um Objekte eines beliebigen skalaren Typs in einen oder aus einem anderen skalaren Typ zu konvertieren.  Explizite Typumwandlungen werden über die gleichen Regeln eingeschränkt, die die Auswirkungen von impliziten Konvertierungen bestimmen.  Zusätzliche Einschränkungen für Typumwandlungen ergeben sich möglicherweise aus den tatsächlichen Größen oder der Darstellung bestimmter Typen.  
  
## Beispiel  
  
```  
// expre_CastOperator.cpp  
// compile with: /EHsc  
// Demonstrate cast operator  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    double x = 3.1;  
    int i;  
    cout << "x = " << x << endl;  
    i = (int)x;   // assign i the integer part of x  
    cout << "i = " << i << endl;  
}  
```  
  
## Beispiel  
  
```  
// expre_CastOperator2.cpp  
// The following sample shows how to define and use a cast operator.   
#include <string.h>  
#include <stdio.h>  
  
class CountedAnsiString  
{  
public:  
    // Assume source is not null terminated  
    CountedAnsiString(const char *pStr, size_t nSize) :  
                      m_nSize(nSize)  
    {  
        m_pStr = new char[sizeOfBuffer];  
  
        strncpy_s(m_pStr, sizeOfBuffer, pStr, m_nSize);  
        memset(&m_pStr[m_nSize], '!', 9); // for demonstration purposes.  
    }  
  
    // Various string-like methods...  
  
    const char *GetRawBytes() const  
    {  
        return(m_pStr);  
    }  
  
    //   
    // operator to cast to a const char *  
    //   
    operator const char *()  
    {  
        m_pStr[m_nSize] = '\0';  
        return(m_pStr);  
    }  
  
    enum  
    {  
        sizeOfBuffer = 20  
    } size;  
  
private:  
    char *m_pStr;  
    const size_t m_nSize;  
};  
  
int main()  
{  
    const char *kStr = "Excitinggg";  
    CountedAnsiString myStr(kStr, 8);  
  
    const char *pRaw = myStr.GetRawBytes();  
    printf_s("RawBytes truncated to 10 chars:   %.10s\n", pRaw);  
  
    const char *pCast = myStr; // or (const char *)myStr;  
    printf_s("Casted Bytes:   %s\n", pCast);  
  
    puts("Note that the cast changed the raw internal string");  
    printf_s("Raw Bytes after cast:   %s\n", pRaw);  
}  
```  
  
  **RawBytes auf 10 Zeichen gekürzt:   Aufregend\!\!**  
**Umgewandelte Bytes:   Aufregend**  
**Beachten Sie, dass die Umwandlung die unformatierte interne Zeichenfolge geändert hat**  
**Nicht formatierte Bytes in Typumwandlung:   Aufregend**   
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Operator für die explizite Typkonvertierung: \(\)](../cpp/explicit-type-conversion-operator-parens.md)   
 [Umwandlungsoperatoren](../cpp/casting-operators.md)   
 [Umwandlungsoperatoren](../c-language/cast-operators.md)