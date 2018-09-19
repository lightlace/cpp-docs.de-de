---
title: Compilerfehler C2047 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2047
dev_langs:
- C++
helpviewer_keywords:
- C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 815973340208aaf7ba498272aef3cd1beebad04d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110860"
---
# <a name="compiler-error-c2047"></a>Compilerfehler C2047

Schlüsselwort "default" ungültig

Das `default` -Schlüsselwort darf nur in einer `switch` -Anweisung enthalten sein.

Im folgenden Beispiel wird C2047 generiert:

```
// C2047.cpp
int main() {
   int i = 0;
   default:   // C2047
   switch(i) {
      case 0:
      break;
   }
}
```

Mögliche Lösung:

```
// C2047b.cpp
int main() {
   int i = 0;
   switch(i) {
      case 0:
      break;
      default:
      break;
   }
}
```