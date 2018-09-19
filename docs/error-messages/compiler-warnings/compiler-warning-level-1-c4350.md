---
title: Compilerwarnung (Stufe 1) C4350 | Microsoft-Dokumentation
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
ms.openlocfilehash: 5ad49a7471be257fa0c22f66fa1bb2bbea049194
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096690"
---
# <a name="compiler-warning-level-1-c4350"></a>Compilerwarnung (Stufe 1) C4350

Verhaltensänderung: 'Member1' wird anstelle von 'Member2' aufgerufen

Ein rvalue-Wert kann nicht auf einen nicht konstanten Verweis gebunden werden. In Versionen von Visual C++ vor Visual Studio 2003 war es möglich, ein Rvalue-Wert auf einen nicht konstanten Verweis in einer direkten Initialisierung zu binden. Dieser Code bietet jetzt eine Warnung.

Um Abwärtskompatibilität zu gewährleisten kann aber dennoch Rvalues an nicht-Const-Verweise gebunden, aber standardkonvertierungen werden bevorzugt, wo immer dies möglich.

Diese Warnung stellt eine Änderung des Verhaltens von der Visual C++ .NET 2002-Compiler dar. Wenn aktiviert, kann diese Warnung möglicherweise für korrekten Code erteilt werden. Z. B. gegeben werden kann, wenn Sie verwenden die **auto_ptr** -Klassenvorlage.

Wenn Sie diese Warnung erhalten, überprüfen Sie den Code aus, um festzustellen, ob sie von der Bindung Rvalues für nicht-Const-Verweise abhängig ist. Der Verweis ein hinzugefügt oder bereitstellt, eine weitere Überladung für Konstante das Problem zu beheben.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Im folgende Beispiel wird die C4350 generiert:

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