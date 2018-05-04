---
title: If-else-Anweisung (C++) | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- else_cpp
- if_cpp
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8de2511096766cc4852c1c612eccb7dc65713218
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="if-else-statement-c"></a>if-else-Anweisung (C++)
Steuert den bedingten Branch. Anweisungen in der *If-Block* werden nur ausgeführt, wenn die *If-Ausdruck* ergibt einen Wert ungleich 0 (oder `true`). Wenn der Wert der *Ausdruck* ungleich NULL ist *statement1* und allen anderen Anweisungen im Block ausgeführt werden und der else-Block, falls vorhanden, wird übersprungen. Wenn der Wert der *Ausdruck* 0 (null), wird der If-Block wird übersprungen, und der else-Block, falls vorhanden, wird ausgeführt. Ausdrücke, die ausgewertet ungleich NULL sind.
- `true`
- ein nicht-Null-Zeiger
- alle arithmetischen Wert ungleich NULL, oder 
- Geben Sie ein Klassentyp, der eine eindeutige Konvertierung in einen arithmetischen, Boolean oder vom Zeigertyp definiert. (Weitere Informationen über Konvertierungen finden Sie unter [Standardkonvertierungen](../cpp/standard-conversions.md).)   
  
## <a name="syntax"></a>Syntax  
  
```  
  
if ( expression )  
{
   statement1;
   ...  
}
else  // optional
{
   statement2;
   ...
} 

// Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )  
{
   statement1;
   ...  
}
else  // optional
{
   statement2;
   ...
}  

// Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
} 
```  
## <a name="example"></a>Beispiel  
```  
// if_else_statement.cpp  
#include <iostream>

using namespace std;

class C
{
    public:
    void do_somthing(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

  // no else statement
    if (x == 10)
    {
        x = 0; 
    }
    
  
    C* c;
  init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```  
## <a name="if-statement-with-an-initializer"></a>Wenn die Anweisung mit einem Initialisierer
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): ein **Wenn** Anweisung enthält möglicherweise auch einen Ausdruck, der eine benannte-Variable deklariert und initialisiert. Verwenden Sie diese Form der If-Anweisung, wenn die Variable nur innerhalb des Bereichs der If-Block erforderlich ist. 

```cpp
## Example  
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>


using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }


    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }

}
```

 In allen Formularen von der **Wenn** -Anweisung *Ausdruck*, wofür einen beliebigen Wert außer einer Struktur wird ausgewertet, einschließlich aller Nebeneffekte. Wird die Steuerung von der **Wenn** Anweisung an die nächste Anweisung im Programm, wenn eines der *Anweisung*s enthält eine [Break](../cpp/break-statement-cpp.md), [zuFortfahren](../cpp/continue-statement-cpp.md), oder [Goto](../cpp/goto-statement-cpp.md).  
  
 Die **else** -Klausel eine `if...else` Anweisung bezieht sich auf die nächstgelegene vorherigen **Wenn** Anweisung im gleichen Bereich, die eine entsprechende keinen **else** -Anweisung.   

## <a name="constexpr-if-statements"></a>Constexpr Wenn Anweisungen
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): In den Funktionsvorlagen, können Sie eine **Constexpr Wenn** -Anweisung zum Zeitpunkt der Kompilierung Verzweigen Entscheidungen ohne müssen mehrere funktionsüberladungen verwenden. Beispielsweise können Sie einer einzelnen Funktion schreiben, diese Handles Parameter Entpacken (keine Überladung von NULL-Parameter ist erforderlich): 

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
// handle t
   do_something(t);

   // handle r conditionally
   constexpr if (sizeof...(r)) 
   {
      
      f(r...); 
   }
   else
   {
       g(r...);
   }
}
```

  
 
## <a name="see-also"></a>Siehe auch  
 [Auswahlanweisungen](../cpp/selection-statements-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [switch-Anweisung (C++)](../cpp/switch-statement-cpp.md)