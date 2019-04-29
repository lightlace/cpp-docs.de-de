---
title: Compilerfehler C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: d2e8b375fd1219b11b3a543bf3a565ddee00ccf2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367953"
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