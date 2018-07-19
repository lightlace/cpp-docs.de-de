---
title: Compilerwarnung (Stufe 1) C4350 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4350
dev_langs:
- C++
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7e13b73eeee9c24841e97419b702b3e41be3982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286928"
---
# <a name="compiler-warning-level-1-c4350"></a>Compilerwarnung (Stufe 1) C4350
Verhaltensänderung: 'Member1' wird anstelle von 'Member2' aufgerufen  
  
 Ein rvalue-Wert kann nicht auf einen nicht konstanten Verweis gebunden werden. In Versionen von Visual C++ vor Visual Studio 2003 war es möglich, ein Rvalue-Wert an einen nicht konstanten Verweis in einer direkten Initialisierung zu binden. Dieser Code gibt jetzt eine Warnung.  
  
 Für die Abwärtskompatibilität es ist weiterhin möglich, Rvalues an nicht Const-Verweise gebunden, aber standardkonvertierungen werden bevorzugt, möglichst.  
  
 Diese Warnung stellt Verhalten unterscheidet sich von der Visual C++ .NET 2002-Compiler dar. Wenn aktiviert, kann diese Warnung möglicherweise für korrekten Code erteilt werden. Z. B. gegeben werden kann, bei Verwendung der **auto_ptr** Klassenvorlage.  
  
 Wenn Sie diese Warnung erhalten, überprüfen Sie den Code aus, um festzustellen, ob die Bindung Rvalues nicht Const-Verweise abhängig. Ein konstanter Verweis für das Hinzufügen oder die Angabe einer zusätzlichen Const-Verweis-Überladung kann das Problem lösen.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
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