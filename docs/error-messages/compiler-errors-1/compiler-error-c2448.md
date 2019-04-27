---
title: Compilerfehler C2448
ms.date: 11/04/2016
f1_keywords:
- C2448
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
ms.openlocfilehash: 915217ffbe848b2814e9960183854e09a80b9ee8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230294"
---
# <a name="compiler-error-c2448"></a>Compilerfehler C2448

"Bezeichner": Funktionsstil-Initialisierung scheint eine Funktionsdefinition zu sein

Definition der Funktion ist falsch.

Dieser Fehler kann durch eine C-Sprachen Parameterliste im alten Stil verursacht werden.

Im folgende Beispiel wird die C2448 generiert:

```
// C2448.cpp
void func(c)
   int c;
{}   // C2448
```