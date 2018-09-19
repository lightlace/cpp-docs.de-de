---
title: Compilerfehler C2085 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d88968e49e38a13782dde2d905a614ad4d177e81
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082377"
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