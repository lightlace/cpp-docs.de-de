---
title: Compilerfehler C2666 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2666
dev_langs:
- C++
helpviewer_keywords:
- C2666
ms.assetid: 78364d15-c6eb-439a-9088-e04a0176692b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17c33f188dbf90e0e7c19ad55e0d14599541ec0d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072731"
---
# <a name="compiler-error-c2666"></a>Compilerfehler C2666

'Bezeichner': Anzahl der Überladungen haben ähnliche Konvertierungen

Einer überladenen Funktion oder Operator ist nicht eindeutig.   Listen der formalen Parameter können auch für den Compiler an, die Mehrdeutigkeit aufzulösen ähnlich sein.  Um diesen Fehler zu beheben, müssen Sie explizit mindestens eine der übergebenen Parameter umgewandelt.

Im folgende Beispiel wird die C2666 generiert:

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

Dieser Fehler kann auch infolge einer konformitätsverbesserung für Compiler generiert werden, die für Visual Studio .NET 2003 durchgeführt wurde:

- binäre Operatoren und benutzerdefinierten Konvertierungen Zeigertypen

- qualifikationskonvertierung ist nicht identisch mit der identitätskonvertierung

Für die binären Operatoren \<, >, \<= und > =, einen übergebenen Parameter wird jetzt implizit konvertiert in den Typ des Operanden den Typ des Parameters in den Typ des Operanden konvertiert einen benutzerdefinierten Konvertierungsoperator definiert. Es gibt jetzt Mehrdeutigkeiten führen.

Rufen Sie für Code, der in der Visual Studio .NET 2003 und Visual Studio .NET der Versionen von Visual C++ gültig ist, des Klasse-Operators, die explizit mit Funktionssyntax ein.

## <a name="example"></a>Beispiel

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

    // Error - Ambiguous call to operator<()
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

## <a name="example"></a>Beispiel

Das folgende Beispiel generiert C2666

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