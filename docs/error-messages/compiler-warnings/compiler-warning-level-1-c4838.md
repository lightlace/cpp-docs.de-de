---
title: Compiler (Stufe 1) C4838 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4838
dev_langs:
- C++
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 227af1840fe5aee63545e35456fe09749f00de1d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4838"></a>Compiler (Stufe 1) C4838
Konvertierung von 'type_1' zu 'type_2' ist eine einschränkende Konvertierung erforderlich.  
  
 Bei Verwendung von Aggregat- oder Liste Initialisierung ist eine implizite einschränkende Konvertierung gefunden.  
  
 Die Programmiersprache C ermöglicht die implizite einschränkende Konvertierungen in Aufgaben und Initialisierung und C++ folgt Farbe, auch wenn unerwartete einschränkende eine viele-Fehler verursacht. Um den Code sicherer zu gestalten, erfordert der C++-standard eine diagnosemeldung, tritt eine einschränkende Konvertierung in einer Initialisierungsliste. In Visual C++ wird die Diagnose [Compiler Fehler C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) Verwendung die einheitliche Initialisierung unterstützte Syntax in Visual Studio 2015 ab. Der Compiler generiert die Warnung C4838 bei der Verwendung der Liste oder aggregatinitialisierung-Syntax, die von Visual Studio 2013 unterstützt.  
  
 Eine einschränkende Konvertierung kann kein Problem sein, wenn Sie wissen, dass die Bandbreite von konvertierten Werten im Ziel eingepasst werden kann. In diesem Fall wissen Sie, mehr als der Compiler durchführt. Wenn Sie eine einschränkende Konvertierung bewusst machen, stellen Sie Ihre Absichten explizite über eine statische Umwandlung. Andernfalls gibt diese Warnung fast immer, dass Sie einen Fehler in Ihrem Code verfügen. Sie können dies beheben, um sicherzustellen, dass die Objekte, die Sie initialisieren Typen aufweisen, die groß genug ist, um die Eingaben zu behandeln sind.  
  
 Im folgenden Beispiel generiert C4838 und zeigt eine Möglichkeit, Fehler zu beheben:  
  
```  
// C4838.cpp -- C++ narrowing conversion diagnostics  
// Compile by using: cl /EHsc C4838.cpp  
  
struct S1 {  
    int m1;  
    double m2, m3;  
};  
  
void function_C4838(double d1) {  
    double ad[] = { 1, d1 }; // OK  
    int ai[] = { 1, d1 };    // warning C4838  
    S1 s11 = { 1, 2, d1 };   // OK  
    S1 s12 { d1, 2, 3 };     // warning C4838  
    S1 s13 { static_cast<int>(d1), 2, 3 }; // possible fix for C4838  
}  
```
