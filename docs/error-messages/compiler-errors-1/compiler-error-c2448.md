---
title: Compilerfehler C2448 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2448
dev_langs:
- C++
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5d3de3b8d4d5d184bb33214679842c557aadf7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135982"
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