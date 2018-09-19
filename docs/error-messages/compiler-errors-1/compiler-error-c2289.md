---
title: Compilerfehler C2289 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2289
dev_langs:
- C++
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5bf284ee7ada4f32772b5f65ed0b983e08e5988
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067604"
---
# <a name="compiler-error-c2289"></a>Compilerfehler C2289

Der gleiche Typqualifizierer wurde mehrmals verwendet

Ein Typqualifizierer (`const`, `volatile`, `signed`oder `unsigned`) wird in einer Typdeklaration oder -definition mehrfach verwendet. Dabei wird bei Einhaltung der ANSI-Kompatibilität (**/Za**) eine Fehlermeldung ausgegeben.

Im folgenden Beispiel wird C2286 generiert:

```
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```