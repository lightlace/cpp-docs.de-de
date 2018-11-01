---
title: Compilerwarnung (Stufe 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: d8c89967e0dc900e098ca03d22932451f26a6a0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531019"
---
# <a name="compiler-warning-level-1-c4377"></a>Compilerwarnung (Stufe 1) C4377

systemeigene Typen sind standardmäßig privat. -d1PrivateNativeTypes ist veraltet.

In früheren Versionen waren systemeigene Typen in Assemblys öffentliche standardmäßig und einer internen, nicht dokumentierten-Compileroption (**/d1PrivateNativeTypes**) wurde verwendet, um diese als privat kennzeichnen.

Alle Typen, systemeigen und CLR sind jetzt standardmäßig in einer Assembly, private damit **/d1PrivateNativeTypes** wird nicht mehr benötigt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4377 generiert.

```
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```