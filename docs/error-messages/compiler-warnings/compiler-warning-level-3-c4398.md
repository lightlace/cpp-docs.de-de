---
title: Compiler-Warnung (Stufe 3) C4398 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 18270bb89bcc5d1855750c572a5b6fb9e51c2ba3
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4398"></a>Compilerwarnung (Stufe 3) C4398
'Variable': Prozessspezifische globale Objekte funktionieren möglicherweise nicht ordnungsgemäß mit mehreren Anwendungsdomänen; __declspec(appdomain) in Betracht  
  
 Eine virtuelle Funktion mit [__clrcall](../../cpp/clrcall.md) -Aufrufkonvention in einem systemeigenen Typ bewirkt die Erstellung einer anwendungsdomänenspezifischen vtable. Eine solche Variable möglicherweise nicht ordnungsgemäß korrigiert, wenn in mehreren Anwendungsdomänen verwendet werden.  
  
 Sie können diese Warnung beheben, indem Sie explizite Markierung der Variablen `__declspec(appdomain)`. In Versionen von Visual Studio vor Visual Studio 2017 können Sie diese Warnung beheben, durch die Kompilierung mit **/CLR: pure**, wodurch globale Variablen pro-Appdomain standardmäßig.  
  
 Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md) und [Anwendungsdomänen und Visual C++](../../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4398 generiert.  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```
