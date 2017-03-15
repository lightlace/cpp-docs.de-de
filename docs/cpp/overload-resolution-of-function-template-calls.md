---
title: "&#220;berladungsaufl&#246;sung von Funktionsvorlagenaufrufen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Auflösung von Funktionsvorlagenüberladungen"
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# &#220;berladungsaufl&#246;sung von Funktionsvorlagenaufrufen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Funktionsvorlage kann nicht auf Vorlagen basierende Funktionen des gleichen Namens überladen.  In diesem Szenario werden Funktionsaufrufe zuerst mithilfe der Vorlagenargumentableitung aufgelöst, um die Funktionsvorlage mit einer eindeutigen Spezialisierung zu instanziieren.  Wenn die Vorlagenargumentableitung fehlschlägt, werden die anderen Funktionsüberladungen zur Auflösung des Aufrufs in Erwägung gezogen.  Zu diesen anderen Überladungen, auch Kandidatensatz genannt, gehören nicht auf Vorlagen basierende Funktionen sowie andere instanziierte Funktionsvorlagen.  Wenn die Vorlagenargumentableitung erfolgreich ist, wird die generierte Funktion mit anderen Funktionen verglichen, um die beste Übereinstimmung nach den Regeln für die Überladungsauflösung zu bestimmen.  Weitere Informationen finden Sie unter [Überladung](../misc/overloading-cpp.md) und [Argumentübereinstimmung](../misc/argument-matching.md).  
  
## Beispiel  
 Wenn eine nicht auf Vorlagen basierende Funktion ein gleich gute Übereinstimmung wie eine Vorlagenfunktion darstellt, wird die nicht auf Vorlagen basierende Funktion ausgewählt \(es sei denn, die Vorlagenargumente wurden explizit angegeben\), wie im Aufruf `f(1, 1)` im folgenden Beispiel gezeigt.  
  
```  
// template_name_resolution9.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
void f(char, char) { cout << "f(char, char)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   f(1, 1);   // Equally good match; choose the nontemplate function.  
   f('a', 1); // Chooses the template function.  
   f<int, int>(2, 2);  // Template arguments explicitly specified.  
}  
```  
  
  **f\(int, int\)**  
**void f\(T1, T2\)**  
**void f\(T1, T2\)**   
## Beispiel  
 Das folgende Beispiel veranschaulicht, dass die genau übereinstimmende Vorlagenfunktion bevorzugt wird, wenn die nicht auf Vorlagen basierende Funktionen eine Konvertierung erfordert.  
  
```  
// template_name_resolution10.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   long l = 0;  
   int i = 0;  
   // Call the template function f(long, int) because f(int, int)  
   // would require a conversion from long to int.  
   f(l, i);  
}  
```  
  
  **void f\(T1, T2\)**   
## Siehe auch  
 [Namensauflösung](../cpp/templates-and-name-resolution.md)   
 [typename](../cpp/typename.md)   
 [Vorlagenargumentableitung](../Topic/Template%20Argument%20Deduction.md)