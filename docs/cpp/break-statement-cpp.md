---
title: "break-Anweisung (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "break_cpp"
  - "break"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "break-Schlüsselwort [C++]"
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# break-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `break`\-Anweisung beendet die Ausführung der nächsten einschließenden Schleife oder Bedingungsanweisung, in der sie angezeigt wird.  Das Steuerelement wird an die Anweisung übergeben, die auf das Ende der Anweisung folgt, falls vorhanden.  
  
## Syntax  
  
```  
break;  
```  
  
## Hinweise  
 Die `break`\-Anweisung wird mit der bedingten [switch](../cpp/switch-statement-cpp.md)\-Anweisung und mit den Schleifenanweisungen [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md) und [while](../cpp/while-statement-cpp.md) verwendet.  
  
 In einer `switch`\-Anweisung bewirkt die `break`\-Anweisung, dass das Programm die nächste Anweisung außerhalb der `switch`\-Anweisung ausführt.  Ohne eine `break`\-Anweisung wird jede Anweisung von der entsprechenden `case`\-Bezeichnung bis zum Ende der `switch`\-Anweisung ausgeführt \(einschließlich der `default`\-Klausel\).  
  
 In Schleifen beendet die `break`\-Anweisung die Ausführung der nächsten einschließenden Anweisung `do`, `for` oder `while`.  Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.  
  
 Innerhalb von geschachtelten Anweisungen beendet die `break`\-Anweisung lediglich die Anweisung `do`, `for`, `switch` oder `while`, von der sie direkt eingeschlossen ist.  Sie können eine `return`\-Anweisung oder eine `goto`\-Anweisung verwenden, um das Steuerelement von tiefer geschachtelten Strukturen zu übergeben.  
  
## Beispiel  
 Im folgenden Code wird die Verwendung der Anweisung `break` in einer `for`\-Schleife veranschaulicht.  
  
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
  
  **In jedem Fall gilt Folgendes:**   
**1**  
**2**  
**3** Im folgenden Code wird die Verwendung von `break` in einer `while`\-Schleife und einer `do`\-Schleife veranschaulicht.  
  
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
  
  **In jedem Fall gilt Folgendes:**  
**0**  
**1**  
**2**  
**3** Im folgenden Code wird die Verwendung von `break` in einer switch\-Anweisung veranschaulicht.  In jedem Fall muss `break` verwendet werden, wenn Sie jeden Fall getrennt behandeln möchten. Wenn Sie `break` nicht verwenden, fällt die Codeausführung auf den nächsten Fall.  
  
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
  
## Siehe auch  
 [Sprunganweisungen](../cpp/jump-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [continue\-Anweisung](../cpp/continue-statement-cpp.md)