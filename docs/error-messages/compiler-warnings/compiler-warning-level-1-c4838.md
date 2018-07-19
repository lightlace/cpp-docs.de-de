---
title: Compilerwarnung (Stufe 1) C4838 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- C4838
dev_langs:
- C++
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1327ed8869c17701c6aa0a6ce2e3479b6109b8cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283844"
---
# <a name="compiler-warning-level-1-c4838"></a>Compilerwarnung (Stufe 1) C4838
Konvertierung von 'type_1' zu 'type_2' ist eine einschränkende Konvertierung erforderlich.  
  
 Eine implizite einschränkende Konvertierung wurde gefunden, bei der Initialisierung von Aggregat oder eine Liste mit.  
  
 Die Programmiersprache C ermöglicht implizite einschränkende Konvertierungen in Zuweisungen und Initialisierung und C++ folgt entsprechen, obwohl unerwarteter einschränkende eine Ursache für viele Codefehlern ist. Um den Code sicherer zu gestalten, erfordert der C++-standard eine diagnosemeldung aus, in einer Initialisierungsliste tritt eine einschränkende Konvertierung. In Visual C++ wird die Diagnose [Compiler Fehler C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) bei Verwendung der einheitliche Initialisierung unterstützten Syntax in Visual Studio 2015 ab. Der Compiler generiert die Warnung C4838, bei der Verwendung der Liste oder ein aggregierter Initialisierung-Syntax, die von Visual Studio 2013 unterstützt.  
  
 Eine einschränkende Konvertierung kann angemessen sein, wenn Sie wissen, dass mögliche konvertierte Wertebereich im Ziel anpassen kann. In diesem Fall wissen Sie mehr als der Compiler übernimmt. Wenn Sie eine einschränkende Konvertierung absichtlich vorgenommen haben, stellen Sie Ihre Absichten explizite mithilfe einer statischen Umwandlung. Andernfalls besagt diese Warnmeldung wird fast immer, dass Sie einen Fehler im Code haben. Sie können Sie beheben, indem Sie sicherstellen, dass die Objekte, die Sie initialisieren aufweisen, die groß genug ist, um die Eingaben zu behandeln sind.  
  
 Im folgende Beispiel wird die C4838 generiert und zeigt eine Möglichkeit, sie diesen Fehler beheben:  
  
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