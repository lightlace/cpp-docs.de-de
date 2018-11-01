---
title: Compilerfehler C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: f82b315a3e7ae4bb1f6d281e1d80ddc2c7fb0dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662913"
---
# <a name="compiler-error-c2619"></a>Compilerfehler C2619

„identifier“: Ein statisches Datenmember ist in einer anonymen Struktur oder Union nicht zulässig.

Ein Member einer anonymen Struktur oder Union ist als `static` deklariert.

Im folgenden Beispiel wird C2619 generiert und veranschaulicht, wie Sie diesen Fehler beheben, indem Sie das statische-Schlüsselwort entfernen.

```
// C2619.cpp
int main() {
   union { static int j; };  // C2619
   union { int j; };  // OK
}
```