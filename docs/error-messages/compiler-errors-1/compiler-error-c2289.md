---
title: Compilerfehler C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: 9fe9b765af72a8864e3e899cafcf648a9facb67e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528127"
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