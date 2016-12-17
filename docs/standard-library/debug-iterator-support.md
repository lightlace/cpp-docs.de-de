---
title: "Unterst&#252;tzung f&#252;r Iteratordebugging"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_HAS_ITERATOR_DEBUGGING symbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unterstützung für Iteratordebugging"
  - "Inkompatible Iteratoren"
  - "Iteratoren, Unterstützung für Iteratordebugging"
  - "Iteratoren, Inkompatibel"
  - "Sichere Bibliotheken"
  - "Sichere Bibliotheken, C++-Standardbibliothek"
  - "Sichere Standard-C++-Bibliothek"
  - "C++-Standardbibliothek, Unterstützung für Iteratordebugging"
ms.assetid: f3f5bd15-4be8-4d64-a4d0-8bc0761c68b6
caps.latest.revision: 22
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# Unterst&#252;tzung f&#252;r Iteratordebugging
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Visual C\+\+\-Laufzeitbibliothek erkennt falsche Iteratorverwendung und erläutert und zeigt ein Dialogfeld zur Laufzeit.  So aktivieren Sie Debuggen Iteratorunterstützung, müssen Sie eine Debugversion einer C\-Laufzeitbibliothek verwenden um das Programm zu kompilieren.  Weitere Informationen finden Sie unter [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md).  Informationen, wie Iteratoren, finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
 Der C\+\+\-Standard beschreibt, z Memberfunktionen möglicherweise Iteratoren einem Container gab, ungültig werden.  Zwei Beispiele sind:  
  
-   Das Löschen eines Elements von einem Container wird Iteratoren zum Element, ungültig werden.  
  
-   Das Erhöhen der Größe von [Vektor](../standard-library/vector.md) \(Das Push\- oder Einfügen\) bewirkt Iteratoren in `vector`, ungültig werden.  
  
## Beispiel  
 Wenn Sie das folgende Programm im Debugmodus kompilieren, zur Laufzeit erläutert er und beendet wird.  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <vector>  
#include <iostream>  
  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   std::vector<int>::iterator i = v.begin();  
   ++i;  
  
   std::vector<int>::iterator j = v.end();  
   --j;  
  
   std::cout<<*j<<'\n';  
  
   v.insert(i,25);   
  
   std::cout<<*j<<'\n'; // Using an old iterator after an insert  
}  
  
```  
  
## Beispiel  
 Sie können das Symbol [\_HAS\_ITERATOR\_DEBUGGING](../standard-library/has-iterator-debugging.md) verwenden, um die Iteratordebuggingsfunktion in einem Debugbuild zu deaktivieren.  Das folgende Programm erläutert, nicht aber haben Trigger des Verhaltens die Definition.  
  
> [!IMPORTANT]
>  mit `_ITERATOR_DEBUG_LEVEL`, `_HAS_ITERATOR_DEBUGGING` zu steuern.  Weitere Informationen finden Sie unter [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
```cpp  
// iterator_debugging.cpp  
// compile with: /EHsc /MDd  
#define _HAS_ITERATOR_DEBUGGING 0  
#include <vector>  
#include <iostream>  
  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   std::vector<int>::iterator i = v.begin();  
   ++i;  
  
   std::vector<int>::iterator j = v.end();  
   --j;  
  
   std::cout<<*j<<'\n';  
  
   v.insert(i,25);   
  
   std::cout<<*j<<'\n'; // Using an old iterator after an insert  
}  
```  
  
  **20**  
**\-572662307**   
## Beispiel  
 Eine Assertion tritt auch auf, wenn Sie versuchen, einen Iterator wie dargestellt zu verwenden, bevor er initialisiert wird, hier:  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <string>  
using namespace std;  
int main() {  
   string::iterator i1, i2;  
   if (i1 == i2)  
      ;  
}  
```  
  
## Beispiel  
 Das folgende Codebeispiel führt eine Assertion, da die beiden Iteratoren zum [for\_each](../Topic/for_each.md) Algorithmus nicht kompatibel sind.  Algorithmen überprüfen, um zu bestimmen, ob die Iteratoren, die ihnen angegeben werden, den gleichen Container verweisen.  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <algorithm>  
#include <vector>  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int> v2;  
  
    v1.push_back(10);  
    v1.push_back(20);  
  
    v2.push_back(10);  
    v2.push_back(20);  
  
    // The next line will assert because v1 and v2 are  
    // incompatible.  
    for_each(v1.begin(), v2.end(), [] (int& elem) { elem *= 2; } );  
}  
```  
  
 Beachten Sie, dass dieses Beispiel den Lambda\-Ausdruck `[] (int& elem) { elem *= 2; }` anstelle eines Feature\-Elements verwendet.  Obwohl diese Auswahl im Assertionsfehler\-ein können Einfluss haben, den so Funktionselement den gleichen Fehler\-lambdas sind sehr nützlich, kompakte Funktionsobjektaufgaben zu erfüllen verursacht.  Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda\-Ausdrücke](../cpp/lambda-expressions-in-cpp.md).  
  
## Beispiel  
 Debuggen Sie den Iterator, der auch überprüft, verursacht eine Iteratorvariable, die in einer `for` \- Schleife deklariert wird, um außerhalb des Arbeitsumfangs sein, wenn der `for` Schleifenbereich beendet.  
  
```cpp  
// debug_iterator.cpp  
// compile with: /EHsc /MDd  
#include <vector>  
#include <iostream>  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   for (std::vector<int>::iterator i = v.begin() ; i != v.end(); ++i)  
   ;  
   --i;   // C2065  
}  
```  
  
## Beispiel  
 Debuggen Sie Iteratoren haben nicht\-triviale Destruktoren.  Wenn ein Destruktor nicht, aus dem Grund immer ausgeführt wird, treten möglicherweise Zugriffsverletzungen und Datenbeschädigungen auf.  Betrachten Sie das folgende Beispiel:  
  
```cpp  
/* compile with: /EHsc /MDd */  
#include <vector>  
struct base {  
   // FIX: uncomment the next line  
   // virtual ~base() {}  
};  
  
struct derived : base {  
   std::vector<int>::iterator m_iter;  
   derived( std::vector<int>::iterator iter ) : m_iter( iter ) {}  
   ~derived() {}  
};  
  
int main() {  
   std::vector<int> vect( 10 );  
   base * pb = new derived( vect.begin() );  
   delete pb;  // doesn't call ~derived()  
   // access violation  
}  
```  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)