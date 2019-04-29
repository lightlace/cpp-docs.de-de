---
title: Compilerfehler C2100
ms.date: 11/04/2016
f1_keywords:
- C2100
helpviewer_keywords:
- C2100
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
ms.openlocfilehash: 89273d5ef9c3b011a7b08a160431dcbc17fc065e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350688"
---
# <a name="compiler-error-c2100"></a>Compilerfehler C2100

ungültige Dereferenzierung.

Dereferenzierungsoperator ( `*` ) wird angewendet auf einen Wert für die kein Zeiger ist.

Im folgende Beispiel wird die C2100 generiert:

```
// C2100.cpp
int main() {
   int r = 0, *s = 0;
   s = &r;
   *r = 200;   // C2100
   *s = 200;   // OK
}
```