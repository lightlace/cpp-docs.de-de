---
title: Compilerwarnung (Stufe 3) C4265
ms.date: 11/04/2016
f1_keywords:
- C4265
helpviewer_keywords:
- C4265
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
ms.openlocfilehash: 8ad07e2a920ed251467c9ffd1d0fb1765557aa7e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051706"
---
# <a name="compiler-warning-level-3-c4265"></a>Compilerwarnung (Stufe 3) C4265

"Class": die Klasse besitzt virtuelle Funktionen, aber der destruktor ist nicht virtuell.

Wenn eine Klasse über virtuelle Funktionen, aber einen nicht virtuellen destruktor verfügt, werden Objekte des Typs möglicherweise nicht ordnungsgemäß zerstört, wenn die Klasse über einen Basisklassen Zeiger zerstört wird.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4265 generiert:

```cpp
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