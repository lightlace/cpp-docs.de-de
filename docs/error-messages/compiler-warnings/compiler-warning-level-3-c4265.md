---
title: Compilerwarnung (Stufe 3) C4265 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4265
dev_langs:
- C++
helpviewer_keywords:
- C4265
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0df54714038ab0fb6020e34aa35d677af5e899b4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016129"
---
# <a name="compiler-warning-level-3-c4265"></a>Compilerwarnung (Stufe 3) C4265

'Klasse': Klasse besitzt virtuelle Funktionen, aber der Destruktor ist nicht virtuell

Wenn eine Klasse virtuelle Funktionen, aber einen nicht virtuellen Destruktor aufweist, können Objekte des Typs nicht ordnungsgemäß gelöscht, wenn die Klasse über einen Zeiger Basisklasse zerstört wird.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgende Beispiel wird die C4265 generiert:

```
// C4265.cpp
// compile with: /W3 /c
#pragma warning(default : 4265)
class B
{
public:
   virtual void vmf();

   ~B();
   // try the following line instead
   // virtual ~B();
};   // C4265

int main()
{
   B b;
}
```