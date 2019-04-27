---
title: Compilerfehler C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: 9fe9b765af72a8864e3e899cafcf648a9facb67e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182794"
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