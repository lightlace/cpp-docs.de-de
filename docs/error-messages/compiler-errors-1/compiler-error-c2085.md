---
title: Compilerfehler C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: 7dbf7266a6330a1fdb46d7f2df90e7684f026d9a
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301963"
---
# <a name="compiler-error-c2085"></a>Compilerfehler C2085

"Identifier": nicht in der formalen Parameterliste.

Der Bezeichner wurde in einer Funktionsdefinition deklariert, aber nicht in der Liste der formalen Parameter. (Nur ANSI C)

Im folgenden Beispiel wird C2085 generiert:

```c
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Mögliche Lösung:

```c
// C2085b.c
void func1( void );
int main( void ) {}
```

Wenn das Semikolon fehlt, sieht `func1()` wie eine Funktionsdefinition, kein Prototyp, aus, sodass `main` in `func1()`definiert ist, und es wird ein Fehler C2085 für den Bezeichner`main`erzeugt.
