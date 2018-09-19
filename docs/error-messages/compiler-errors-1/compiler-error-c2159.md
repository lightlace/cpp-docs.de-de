---
title: Compilerfehler C2159 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2159
dev_langs:
- C++
helpviewer_keywords:
- C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c33f8faebbca2999a893ceb1d0650ba89ee74bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048486"
---
# <a name="compiler-error-c2159"></a>Compilerfehler C2159

Mehr als eine Speicherklasse angegeben

Eine Deklaration enthält mehr als eine Speicherklasse.

Im folgenden Beispiel wird C2159 generiert:

```
// C2159.cpp
// compile with: /c
static int i;   // OK
extern static int i;   // C2159
```