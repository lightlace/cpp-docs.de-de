---
title: break-Anweisung (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- break_cpp
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2e016ccc90ef53ca5f269a73d3f5b7ed3185f550
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="break-statement-c"></a>break-Anweisung (C++)
Die `break`-Anweisung beendet die Ausführung der nächsten einschließenden Schleife oder Bedingungsanweisung, in der sie angezeigt wird. Das Steuerelement wird an die Anweisung übergeben, die auf das Ende der Anweisung folgt, falls vorhanden.  
  
## <a name="syntax"></a>Syntax  
  
```  
break;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `break` Anweisung wird verwendet, mit der bedingten [wechseln](../cpp/switch-statement-cpp.md) Anweisung und mit der [führen](../cpp/do-while-statement-cpp.md), [für](../cpp/for-statement-cpp.md), und [während](../cpp/while-statement-cpp.md) Schleife -Anweisungen.  
  
 In einer `switch`-Anweisung bewirkt die `break`-Anweisung, dass das Programm die nächste Anweisung außerhalb der `switch`-Anweisung ausführt. Ohne eine `break`-Anweisung wird jede Anweisung von der entsprechenden `case`-Bezeichnung bis zum Ende der `switch`-Anweisung ausgeführt (einschließlich der `default`-Klausel).  
  
 In Schleifen beendet die `break`-Anweisung die Ausführung der nächsten einschließenden Anweisung `do`, `for` oder `while`. Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.  
  
 Innerhalb von geschachtelten Anweisungen beendet die `break`-Anweisung lediglich die Anweisung `do`, `for`, `switch` oder `while`, von der sie direkt eingeschlossen ist. Sie können eine `return`-Anweisung oder eine `goto`-Anweisung verwenden, um das Steuerelement von tiefer geschachtelten Strukturen zu übergeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird die Verwendung der Anweisung `break` in einer `for`-Schleife veranschaulicht.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // An example of a standard for loop  
    for (int i = 1; i < 10; i++)  
    {  
        cout << i << '\n';  
        if (i == 4)  
            break;  
    }  
  
    // An example of a range-based for loop  
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};  
  
    for (int i : nums) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
    }  
}  
```  
  
```Output  
In each case:   
1  
2  
3  
```  
  
 Im folgenden Code wird die Verwendung von `break` in einer `while`-Schleife und einer `do`-Schleife veranschaulicht.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    int i = 0;  
  
    while (i < 10) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    }  
  
    i = 0;  
    do {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    } while (i < 10);  
}  
```  
  
```Output  
In each case:  
0123  
```  
  
 Im folgenden Code wird die Verwendung von `break` in einer switch-Anweisung veranschaulicht. In jedem Fall muss `break` verwendet werden, wenn Sie jeden Fall getrennt behandeln möchten. Wenn Sie `break` nicht verwenden, fällt die Codeausführung auf den nächsten Fall.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
enum Suit{ Diamonds, Hearts, Clubs, Spades };  
  
int main() {  
  
    Suit hand;  
    . . .  
    // Assume that some enum value is set for hand  
    // In this example, each case is handled separately  
    switch (hand)  
    {  
    case Diamonds:  
        cout << "got Diamonds \n";  
        break;  
    case Hearts:  
        cout << "got Hearts \n";  
        break;  
    case Clubs:  
        cout << "got Clubs \n";  
        break;  
    case Spades:  
        cout << "got Spades \n";  
        break;  
    default:   
          cout << "didn't get card \n";  
    }  
    // In this example, Diamonds and Hearts are handled one way, and  
    // Clubs, Spades, and the default value are handled another way  
    switch (hand)  
    {  
    case Diamonds:  
    case Hearts:  
        cout << "got a red card \n";  
        break;  
    case Clubs:  
    case Spades:   
    default:  
        cout << "didn't get a red card \n";  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Sprunganweisungen](../cpp/jump-statements-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [continue-Anweisung](../cpp/continue-statement-cpp.md)
