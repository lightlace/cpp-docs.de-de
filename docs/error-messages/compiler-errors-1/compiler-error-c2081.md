---
title: Compilerfehler C2081 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2081
dev_langs:
- C++
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48f2cdecaea38beed14735bb3f94c8422a28c747
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030455"
---
# <a name="compiler-error-c2081"></a>Compilerfehler C2081

'Bezeichner': Name in der formalen Parameterliste ist ungültig

Der Bezeichner verursacht einen Syntaxfehler.

Dieser Fehler kann verursacht werden, mithilfe des alten Stils für die Liste der formalen Parameter. Sie müssen den Typ der formalen Parameter in der Liste der formalen Parameter angeben.

Im folgende Beispiel wird die C2081 generiert:

```
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

Mögliche Lösung:

```
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```