---
title: Compilerwarnung (Stufe 3) C4398 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ace2df75b5d2579b66a4d3930470021726ba4c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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