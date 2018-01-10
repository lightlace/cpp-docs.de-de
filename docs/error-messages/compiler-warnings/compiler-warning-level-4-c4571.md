---
title: Compilerwarnung (Stufe 4) C4571 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4571
dev_langs: C++
helpviewer_keywords: C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cab2068b6117f092dcc098591bb620156b2c0cf6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4571"></a>Compilerwarnung (Stufe 4) C4571
Information: catch(...)-Semantik seit Visual C++ 7.1 geändert; strukturierte Ausnahmen (SEH) werden nicht mehr abgefangen.  
  
 C4571 wird für jeden catch(...) beim Kompilieren mit **/EHs**.  
  
 Beim Kompilieren mit **/EHs**, ein wird kein catch(...) eine strukturierte Ausnahme (aufgrund einer Division durch Null, null-Zeiger, z. B.), einem catch(...) Block wird nur Catch explizit ausgelöst, C++-Ausnahmen.  Weitere Informationen finden Sie unter [Ausnahmebehandlung (Task Parallel Library)](../../cpp/exception-handling-in-visual-cpp.md).  
  
 Diese Warnung ist standardmäßig deaktiviert.  Aktivieren Sie diese Warnung auf, um sicherzustellen, dass bei der Kompilierung **/EHs** Ihre Catch (...)-Blöcken beabsichtigen nicht, um strukturierte Ausnahmen abzufangen.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Sie können in einem der folgenden Arten C4571 behoben haben,  
  
-   Kompilieren Sie mit **/EHa** Falls Sie weiterhin Ihre catch(...)-Blöcke zum Abfangen von strukturierter Ausnahmen benötigen.  
  
-   Aktivieren Sie C4571 nicht, wenn Sie nicht möchten, dass Ihre catch(...)-Blöcke zum strukturierte Ausnahmen abfangen, jedoch weiterhin catch(...) Blöcke verwenden möchten.  Sie können auch weiterhin abfangen strukturierte Ausnahmen, die mit den Schlüsselwörtern für die strukturierte Ausnahmebehandlung (**__try**, **__except**, und **__finally**).  Beachten Sie jedoch, dass kompiliert **/EHs** Destruktoren werden nur aufgerufen werden, wenn eine C++-Ausnahme ausgelöst wird, nicht verwendet werden, wenn eine SEH-Ausnahme tritt auf,.  
  
-   Catch-Blöcke für C++-Ausnahmen, die bestimmte catch(...) Block ersetzt, und optional hinzufügen, um die C++-Ausnahmebehandlung die strukturierten Ausnahmebehandlung (**__try**, **__except**, und **_ __identifier**).  Finden Sie unter [strukturierte Ausnahmebehandlung (C/C++)](../../cpp/structured-exception-handling-c-cpp.md) für Weitere Informationen.  
  
 Finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4571 generiert.  
  
```  
// C4571.cpp  
// compile with: /EHs /W4 /c  
#pragma warning(default : 4571)  
int main() {  
   try {  
      int i = 0, j = 1;  
      j /= i;   // this will throw a SE (divide by zero)  
   }  
   catch(...) {}   // C4571 warning  
}  
```