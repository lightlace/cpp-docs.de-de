---
title: Compilerfehler C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: ed307f46db1261d79d5b0ec6b36852cac2e6d13e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776118"
---
# <a name="compiler-error-c3622"></a>Compilerfehler C3622

'Klasse': eine Klasse deklariert werden, da 'Schlüsselwort' kann nicht instanziiert werden

Es wurde versucht, zum Instanziieren einer Klasse, die als [abstrakte](../../extensions/abstract-cpp-component-extensions.md). Eine Klasse als markiert `abstract` kann eine Basisklasse sein, aber nicht instanziiert werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3622 generiert.

```
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
