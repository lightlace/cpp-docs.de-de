---
title: Compilerwarnung (Stufe 2) C4302
ms.date: 11/04/2016
f1_keywords:
- C4302
helpviewer_keywords:
- C4302
ms.assetid: f5e1c939-e134-4cca-ba1e-9b15a81549ae
ms.openlocfilehash: 68143499c3e22316b443a4c1b55cac6e142552cb
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052085"
---
# <a name="compiler-warning-level-2-c4302"></a>Compilerwarnung (Stufe 2) C4302

' Konvertierung ': Abschneiden von ' Type 1 ' in ' Type 2 '

Der Compiler hat eine Konvertierung von einem größeren Typ in einen kleineren Typ erkannt. Informationen können verloren gehen.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4302 generiert:

```cpp
// C4302.cpp
// compile with: /W2
#pragma warning(default : 4302)
int main() {
   int i;
   char c = (char) &i;     // C4302
   short s = (short) &i;   // C4302
}
```