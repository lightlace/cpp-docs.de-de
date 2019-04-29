---
title: Compilerfehler C2034
ms.date: 11/04/2016
f1_keywords:
- C2034
helpviewer_keywords:
- C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
ms.openlocfilehash: 4b4fe769f78e5f826ba08d4819019210f21f860f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400473"
---
# <a name="compiler-error-c2034"></a>Compilerfehler C2034

'Bezeichner': Typ des Bitfelds ist zu klein für die Anzahl von Bits

Die Anzahl der Bits in der Deklaration Bitfeld überschreitet die Größe des Basistyps.

Im folgende Beispiel wird die C2034 generiert:

```
// C2034.cpp
struct A {
   char test : 9;   // C2034, char has 8 bits
};
```

Mögliche Lösung:

```
// C2034b.cpp
// compile with: /c
struct A {
   char test : 8;
};
```