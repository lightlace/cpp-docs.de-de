---
title: "__if_exists-Anweisung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_exists_cpp"
  - "__if_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_exists-Schlüsselwort [C++]"
  - "Bezeichner, Testen auf Vorhandensein"
  - "Symbole, Testen auf Vorhandensein"
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __if_exists-Anweisung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `__if_exists`\-Anweisung testet, ob der angegebene Bezeichner vorhanden ist.  Wenn der Bezeichner vorhanden ist, wird der angegebene Anweisungsblock ausgeführt.  
  
## Syntax  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`identifier`|Der Bezeichner, dessen Vorhandensein Sie überprüfen möchten.|  
|`statements`|Eine oder mehrere Anweisungen, die auszuführen sind, wenn `identifier` vorhanden ist.|  
  
## Hinweise  
  
> [!CAUTION]
>  Um die zuverlässigsten Ergebnisse zu erzielen, verwenden Sie die `__if_exists`\-Anweisung mit den folgenden Einschränkungen.  
  
-   Wenden Sie die `__if_exists`\-Anweisung nur auf einfache Typen, nicht auf Vorlagen an.  
  
-   Wenden Sie die `__if_exists`\-Anweisung auf Bezeichner innerhalb oder außerhalb einer Klasse an.  Übernehmen Sie die `__if_exists`\-Anweisung nicht für lokale Variablen.  
  
-   Verwenden Sie die `__if_exists`\-Anweisung nur im Text einer Funktion.  Außerhalb des Texts einer Funktion kann die `__if_exists`\-Anweisung nur vollständig definierte Typen testen.  
  
-   Wenn Sie auf überladene Funktionen testen, können Sie nicht auf eine bestimmte Form der Überladung testen.  
  
 Die Ergänzung zur `__if_exists`\-Anweisung ist die Anweisung [\_\_if\_not\_exists](../cpp/if-not-exists-statement.md).  
  
## Beispiel  
 Beachten Sie, dass in diesem Beispiel Vorlagen verwendet werden, was nicht empfohlen wird.  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## Output  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## Siehe auch  
 [Auswahlanweisungen](../cpp/selection-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [\_\_if\_not\_exists\-Anweisung](../cpp/if-not-exists-statement.md)