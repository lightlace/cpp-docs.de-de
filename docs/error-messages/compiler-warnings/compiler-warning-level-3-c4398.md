---
title: Compilerwarnung (Stufe 3) C4398 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4398
dev_langs: C++
helpviewer_keywords: C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d5ce6355e50c1ea2594820388edc34c69ea0e899
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4398"></a>Compilerwarnung (Stufe 3) C4398
'Variable': prozessspezifisch globales Objekt möglicherweise nicht ordnungsgemäß mit mehreren Anwendungsdomänen; Erwägen Sie __declspec(appdomain)  
  
 Eine virtuelle Funktion mit [__clrcall](../../cpp/clrcall.md) -Aufrufkonvention in einem systemeigenen Typ bewirkt die Erstellung einer pro Anwendung Domäne Vtable. Eine solche Variable möglicherweise nicht ordnungsgemäß korrigiert werden, wenn in mehreren Anwendungsdomänen verwendet.  
  
 Sie können diese Warnung beheben, indem Sie explizite Markierung der Variablen `__declspec(appdomain)`. In Versionen von Visual Studio vor Visual Studio 2017, können Sie diese Warnung beheben, durch die Kompilierung mit **/CLR: pure**, wodurch globale Variablen pro-Appdomain standardmäßig.  
  
 Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md) und [Anwendungsdomänen und Visual C++](../../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4398 generiert.  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```