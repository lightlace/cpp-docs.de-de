---
title: Compilerfehler C2048 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2048
dev_langs:
- C++
helpviewer_keywords:
- C2048
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dca0cf7e95f2a876760415d5c628287fab47227c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055831"
---
# <a name="compiler-error-c2048"></a>Compilerfehler C2048

Mehrere Vorkommen von default

Eine `switch` -Anweisung enthält mehrere `default` -Bezeichnungen. Löschen Sie eine der `default` Bezeichnungen, um den Fehler zu beheben.

Im folgenden Beispiel wird C2048 generiert:

```
// C2048.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
      default:   // C2048
         a = 3;
   }
}
```

Mögliche Lösung:

```
// C2048b.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```