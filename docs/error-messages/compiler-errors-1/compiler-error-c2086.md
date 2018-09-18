---
title: Compilerfehler C2086 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2086
dev_langs:
- C++
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0e0d8b105d58b0585bc31b8d340d3d7ba5fb29e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029844"
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