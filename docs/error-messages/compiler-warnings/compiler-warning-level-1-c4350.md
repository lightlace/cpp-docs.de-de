---
title: Compilerwarnung (Stufe 1) C4350 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4350
dev_langs:
- C++
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 141f5552c4b86e170587f42ebabf5e2e597b4e96
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4350"></a>Compilerwarnung (Stufe 1) C4350
Verhaltensänderung: 'Member1' wird anstelle von 'Member2' aufgerufen  
  
 Ein rvalue-Wert kann nicht auf einen nicht konstanten Verweis gebunden werden. In Versionen von Visual C++ vor Visual Studio 2003 war es möglich, ein Rvalue-Wert an einen nicht konstanten Verweis in einer direkten Initialisierung zu binden. Dieser Code gibt jetzt eine Warnung.  
  
 Für die Abwärtskompatibilität es ist weiterhin möglich, Rvalues an nicht Const-Verweise gebunden, aber standardkonvertierungen werden bevorzugt, möglichst.  
  
 Diese Warnung stellt Verhalten unterscheidet sich von der Visual C++ .NET 2002-Compiler dar. Wenn aktiviert, kann diese Warnung möglicherweise für korrekten Code erteilt werden. Z. B. gegeben werden kann, bei Verwendung der **auto_ptr** Klassenvorlage.  
  
 Wenn Sie diese Warnung erhalten, überprüfen Sie den Code aus, um festzustellen, ob die Bindung Rvalues nicht Const-Verweise abhängig. Ein konstanter Verweis für das Hinzufügen oder die Angabe einer zusätzlichen Const-Verweis-Überladung kann das Problem lösen.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler deaktivierte Compilerwarnungen standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Beispiel wird C4350 generiert:  
  
```cpp  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead:  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```
