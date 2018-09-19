---
title: Compilerfehler C2511 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b628adda383baee0f2ec03ace715d94c6cca764c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058145"
---
# <a name="compiler-error-c2511"></a>Compilerfehler C2511

"Bezeichner": überladene Memberfunktion nicht in "Klasse" gefunden.

Keine Version der Funktion wird mit den angegebenen Parametern deklariert werden.  Mögliche Ursachen:

1. Falsche Parameter an die Funktion übergeben.

1. Parameter, die in der falschen Reihenfolge übergeben werden.

1. Falsche Schreibweise für Parameternamen.

Im folgende Beispiel wird die C2511 generiert:

```
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```