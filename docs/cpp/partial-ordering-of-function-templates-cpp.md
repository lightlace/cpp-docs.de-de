---
title: "Partielle Reihenfolge von Funktionsvorlagen (C++)"
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
  - "Partielle Reihenfolge von Funktionsvorlagen"
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Partielle Reihenfolge von Funktionsvorlagen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es können mehrere Funktionsvorlagen, die der Argumentliste eines Funktionsaufrufs entsprechen, verfügbar sein.  C\+\+ definiert eine partielle Reihenfolge von Funktionsvorlagen, um anzugeben, welche Funktion aufgerufen werden soll.  Die Reihenfolge ist partiell, da es mehrere Vorlagen geben kann, die als genauso spezialisiert betrachtet werden.  
  
 Der Compiler wählt die speziellste Vorlagenfunktion aus, die aus den möglichen Übereinstimmungen verfügbar ist.  Wenn z. B. eine Funktionsvorlage einen Typ **T** akzeptiert, und eine andere Funktionsvorlage, die **T\*** akzeptiert, verfügbar ist, gilt die **T\***\-Version als spezialisierter und ist der generischen **T**\-Version vorzuziehen, wenn das Argument ein Zeigertyp ist, auch wenn beide Übereinstimmungen zulässig wären.  
  
 Verwenden Sie folgenden Prozess, um zu ermitteln, ob ein Funktionsvorlagenkandidat spezialisierter ist:  
  
1.  Berücksichtigen Sie zwei Funktionsvorlagen, T1 und T2.  
  
2.  Ersetzen Sie die Parameter in T1 durch einen hypothetischen eindeutigen Typ X.  
  
3.  Überprüfen Sie mit der Parameterliste in T1, ob T2 eine gültige Vorlage für diese Parameterliste ist.  Ignorieren Sie alle impliziten Konvertierungen.  
  
4.  Wiederholen Sie den gleichen Prozess umgekehrt mit T1 und T2.  
  
5.  Wenn eine Vorlage eine gültige Vorlagenargumentliste für die andere Vorlage ist, das Gegenteil aber nicht zutrifft, wird die Vorlage als weniger spezialisiert angesehen als die andere Vorlage.  Wenn beide Vorlagen mit dem vorherigen Schritt gültige Argumente füreinander bilden, werden sie als einheitlich spezialisiert behandelt, und der Versuch, sie zu verwenden, führt zu einem mehrdeutigen Aufruf.  
  
6.  Mithilfe dieser Regeln können Sie:  
  
    1.  Eine Vorlagenspezialisierung für einen bestimmten Typ ist spezialisierter als eine, die ein generisches Typargument verwendet.  
  
    2.  Eine Vorlage, die nur **T\*** akzeptiert, ist spezialisierter als eine, die nur **T** akzeptiert, da ein hypothetischer Typ **X\*** ein gültiges Argument für ein **T** Vorlagenargument ist, aber **X** kein gültiges Argument für ein **T\***\-Vorlagenargument ist.  
  
    3.  **const T** ist spezialisierter als **T**, da **const X** ein gültiges Argument für ein **T**\-Vorlagenargument ist, aber **X** kein gültiges Argument für ein **const T**\-Vorlagenargument ist.  
  
    4.  **const T\*** ist spezialisierter als **T\***, da **const X\*** ein gültiges Argument für ein **T\***\-Vorlagenargument ist, aber **X\*** kein gültiges Argument für ein **const T\***\-Vorlagenargument ist.  
  
7.  Das folgende Beispiel funktioniert in Visual C\+\+ .NET 2003, wie im Standard angegeben:  
  
```  
// partial_ordering_of_function_templates.cpp  
// compile with: /EHsc  
#include <iostream>  
  
extern "C" int printf(const char*,...);  
template <class T> void f(T) {  
   printf_s("Less specialized function called\n");  
}  
  
template <class T> void f(T*) {  
   printf_s("More specialized function called\n");  
}  
  
template <class T> void f(const T*) {  
   printf_s("Even more specialized function for const T*\n");  
}  
  
int main() {  
   int i =0;  
   const int j = 0;  
   int *pi = &i;  
   const int *cpi = &j;  
  
   f(i);   // Calls less specialized function.  
   f(pi);  // Calls more specialized function.  
   f(cpi); // Calls even more specialized function.  
   // Without partial ordering, these calls would be ambiguous.  
}  
```  
  
### Output  
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## Siehe auch  
 [Funktionsvorlagen](../cpp/function-templates.md)