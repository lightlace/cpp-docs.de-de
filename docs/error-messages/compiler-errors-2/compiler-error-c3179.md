---
title: Compilerfehler C3179 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3179
dev_langs:
- C++
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed09f1557c2a86d144d5ff4ee476bd8c3fa0f650
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116580"
---
# <a name="compiler-error-c3179"></a>Compilerfehler C3179

Ein unbenannter verwalteter oder WinRT-Typ ist nicht zulässig.

Alle CLR- und WinRT-Klassen und -Strukturen müssen Namen haben.

Im folgenden Beispiel wird C3179 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3179a.cpp
// compile with: /clr /c
typedef value struct { // C3179
// try the following line instead
// typedef value struct MyStruct {
   int i;
} V;
```
