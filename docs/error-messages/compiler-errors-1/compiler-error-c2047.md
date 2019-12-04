---
title: Compilerfehler C2047
ms.date: 11/04/2016
f1_keywords:
- C2047
helpviewer_keywords:
- C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
ms.openlocfilehash: b6e531487038ab7610be3c79b5acdd85d1073de4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740116"
---
# <a name="compiler-error-c2047"></a>Compilerfehler C2047

Schlüsselwort "default" ungültig

Das `default` -Schlüsselwort darf nur in einer `switch` -Anweisung enthalten sein.

Im folgenden Beispiel wird C2047 generiert:

```cpp
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

```cpp
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
