---
title: Compilerfehler C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: 094a794627b886abc7db5ba4d74c6fe97ff82461
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216125"
---
# <a name="compiler-error-c2086"></a>Compilerfehler C2086

'Bezeichner': Neudefinition

Der Bezeichner mehrfach definiert ist, oder eine nachfolgende Deklaration unterscheidet sich von einer vorherigen.

C2086 können auch das Ergebnis der inkrementellen Erstellung einer referenzierten C#-Assembly sein. Erstellen Sie die C#-Assembly zum Beheben dieses Fehlers neu.

Im folgende Beispiel wird die C2086 generiert:

```
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```