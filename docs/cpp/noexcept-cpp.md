---
title: "noexcept (C++)"
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
  - "noexcept_cpp"
dev_langs: 
  - "C++"
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# noexcept (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C \+\+ 11:** Gibt an, ob eine Funktion Ausnahmen auslösen kann.  
  
## Syntax  
  
```vb  
ReturnType FunctionName(params) noexcept;  
ReturnType FunctionName(params) noexcept(noexcept(expression);  
```  
  
#### Parameter  
 expression  
 Ein konstanter Ausdruck, der als TRUE oder FALSE ausgewertet wird.  Die Version ohne Bedingung entspricht noexcept\(true\).  
  
## Hinweise  
 `noexcept` \(und das Synonym `noecept(true)`\) geben an, dass die Funktion nie eine Ausnahme auslöst oder eine Ausnahme von einer anderen Funktion zulässt, die direkt oder indirekt aufgerufen wird.  Genauer gesagt bedeutet `noexcept`, dass die Funktion nur `noexcept` ist, wenn sie alle aufgerufenen Funktionen auch noexcept oder const sind, und keine potenziell ausgewerteten dynamischen Umwandlungen vorhanden sind, die eine Laufzeitprüfung erfordern, keine auf einen glvalue\-Ausdruck angewendeten typeid\-Ausdrücke, dessen Typ ein polymorpher Klassentyp ist, oder ausgelösten Ausdrücke vorhanden sind.  Der Compiler überprüft nicht unbedingt jeden Codepfad auf Ausnahmen, die sich auf eine `noexcept`\-Funktion auswirken können.  Wenn eine Ausnahme eine als `noexcept` gekennzeichnete Funktion erreicht, wird [std::terminate](../Topic/terminate%20\(%3Cexception%3E\).md) sofort aufgerufen, und es kann nicht garantiert werden, dass die Destruktoren aller im Gültigkeitsbereich enthaltenen Objekte aufgerufen werden.  
  
 Eine mit bedingtem noexcept\-Objekt deklarierte Funktion, das noexcept\(false\) zurückgibt, gibt an, dass keine Ausnahmen übergeben werden dürfen.  Beispiel: Eine Funktion, die ihre Argumente kopiert, ist möglicherweise als noexcept unter der Bedingung deklariert, dass das kopierte Objekt vom Typ Plain Old Data Type \(POD\) ist.  Eine solche Funktion kann wie folgt deklariert werden:  
  
```  
#include <type_traits>  
  
template <typename T>  
T copy_object(T& obj) noexcept(std::is_pod<T>)  
{  
 //. . .   
}  
  
```  
  
 Verwenden Sie `noexcept` anstelle des Ausnahmespezifizierers `throw`, der in C\+\+11 und höher veraltet ist  Es wird empfohlen, `noexcept` auf eine Funktion anzuwenden, wenn sichergestellt werden kann, dass eine Ausnahme in der Aufrufliste nie nach oben weitergegeben wird.  Mit einer mit `noexcept` deklarierten Funktion können Compiler effizienter Code in verschiedenen anderen Kontexten generieren.  
  
## Siehe auch  
 [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)