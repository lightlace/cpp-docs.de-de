---
title: Compilerfehler C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: a65e3c0ea622950b99b9ba83fc168b4718d13e46
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345708"
---
# <a name="compiler-error-c2085"></a>Compilerfehler C2085

'Bezeichner': nicht in der Liste formaler Parameter

Der Bezeichner wurde in einer Funktionsdefinition, aber nicht in der Liste formaler Parameter deklariert. (Nur ANSI-C)

Im folgende Beispiel wird die C2085 generiert:

```
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Mögliche Lösung:

```
// C2085b.c
void func1( void );
int main( void ) {}
```

Das Semikolon fehlt, `func1()` ähnelt einer Funktionsdefinition, nicht um einen Prototyp, also `main` definiert ist `func1()`, generieren Fehler C2085 für Bezeichner `main`.