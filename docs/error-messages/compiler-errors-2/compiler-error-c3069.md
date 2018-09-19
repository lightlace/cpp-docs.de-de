---
title: Compilerfehler C3069 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3069
dev_langs:
- C++
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19deba44883d7b6815d7453e4bb231043eb7c75e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078906"
---
# <a name="compiler-error-c3069"></a>Compilerfehler C3069

"Operator": Für den Enumerationstyp nicht zulässig

Ein Operator wird für CLR-Enumerationen nicht unterstützt.  Weitere Informationen finden Sie unter [wie: definieren und Verarbeiten von Enumerationen in C++ / CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3069 generiert:

```
// C3069.cpp
// compile with: /clr
enum struct E { e1 };
enum F { f1 };

int main() {
   E e = E::e1;
   bool tf;
   tf = !e;   // C3069

   // supported for native enums
   F f = f1;
   tf = !f;
}
```