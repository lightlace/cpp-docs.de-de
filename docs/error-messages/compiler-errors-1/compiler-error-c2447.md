---
title: Compilerfehler C2447
ms.date: 11/04/2016
f1_keywords:
- C2447
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
ms.openlocfilehash: 14fec374927fc798956a249773d9bec814e7a823
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744185"
---
# <a name="compiler-error-c2447"></a>Compilerfehler C2447

"{": Funktionskopf fehlt - Parameterliste im alten Stil?

Der Compiler hat eine unerwartete öffnende geschweifte Klammer im globalen Bereich festgestellt. In den meisten Fällen wird dieser Fehler aufgrund eines falsch formatierten Funktionsheaders, einer falsch platzierten Deklaration oder eines fehlgeleiteten Semikolons verursacht. Stellen Sie zur Behebung dieses Problems sicher, dass die öffnende Klammer einem ordnungsgemäß formatierten Funktionsheader folgt und ihr weder eine Deklaration noch ein fehlgeleitetes Semikolon vorangeht.

Dieser Fehler kann auch von einer formalen C-Argumentliste im alten Stil verursacht werden. Gestalten Sie zur Behebung dieses Problems die Argumentliste um. Der moderne Stil sieht runde Klammern vor.

Im folgenden Beispiel wird C2447 generiert:

```cpp
// C2447.cpp
int c;
{}       // C2447
```
