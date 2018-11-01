---
title: Compilerfehler C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: d2e8b375fd1219b11b3a543bf3a565ddee00ccf2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502062"
---
# <a name="compiler-error-c2459"></a>Compilerfehler C2459

'Bezeichner': definiert wird; als zusätzliches anonymes Element kann nicht hinzugefügt werden.

Eine Klasse, Struktur oder Union wird in einen eigenen Bereich von einem Mitglied einer anonymen Union neu definiert.

Im folgende Beispiel wird die C2459 generiert:

```
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```