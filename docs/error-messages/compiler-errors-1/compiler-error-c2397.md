---
title: Compilerfehler Fehler C2397 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2397
dev_langs: C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 31f2b548fd13bc7702d44ef4a6d5dc5c34a5eb3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2397"></a>Compilerfehler Fehler C2397
Konvertierung von 'type_1' zu 'type_2' ist eine einschränkende Konvertierung erforderlich.  
  
 Eine implizite einschränkende Konvertierung wurde gefunden, wenn Sie einheitliche Initialisierung verwenden.  
  
 Die Programmiersprache C ermöglicht implizite einschränkende Konvertierungen in Zuweisungen und Initialisierung und C++ folgt entsprechen, obwohl unerwarteter einschränkende eine Ursache für viele Codefehlern ist. Um den Code sicherer zu gestalten, erfordert der C++-standard eine diagnosemeldung aus, in einer Initialisierungsliste tritt eine einschränkende Konvertierung. In Visual C++ wird die Diagnose Compiler Fehler C2397 Anfang unterstützte Syntax einheitliche Initialisierung in Visual Studio 2015 zu verwenden. Der Compiler generiert [Compilerwarnung (Stufe 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) bei der Verwendung der Liste oder ein aggregierter Initialisierung-Syntax, die von Visual Studio 2013 unterstützt.  
  
 Eine einschränkende Konvertierung kann angemessen sein, wenn Sie wissen, dass mögliche konvertierte Wertebereich im Ziel anpassen kann. In diesem Fall wissen Sie mehr als der Compiler übernimmt. Wenn Sie eine einschränkende Konvertierung absichtlich vorgenommen haben, stellen Sie Ihre Absichten explizite mithilfe einer statischen Umwandlung. Andernfalls gibt diese Fehlermeldung fast immer, dass Sie einen Fehler im Code haben. Sie können Sie beheben, indem Sie sicherstellen, dass die Objekte, die Sie initialisieren aufweisen, die groß genug ist, um die Eingaben zu behandeln sind.  
  
 Im folgende Beispiel wird die C2397 generiert und zeigt eine Möglichkeit, sie diesen Fehler beheben:  
  
```  
// C2397.cpp -- C++ narrowing conversion diagnostics  
// Compile by using: cl /EHsc C2397.cpp  
#include <vector>   
  
struct S1 {  
    int m1;  
    double m2, m3;  
};  
  
void function_C2397(double d1) {  
    char c1 { 127 };          // OK  
    char c2 { 513 };          // error C2397  
  
    std::vector<S1> vS1;  
    vS1.push_back({ d1, 2, 3 }); // error C2397  
  
    // Possible fix if you know d1 always fits in an int  
    vS1.push_back({ static_cast<int>(d1), 2, 3 });   
}  
```