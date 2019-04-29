---
title: Compilerfehler C2447
ms.date: 11/04/2016
f1_keywords:
- C2447
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
ms.openlocfilehash: 64dca8313af8b640b7b03c1ab27a1a31fa90de09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301967"
---
# <a name="compiler-error-c2447"></a>Compilerfehler C2447

"{": Funktionskopf fehlt - Parameterliste im alten Stil?

Der Compiler hat eine unerwartete öffnende geschweifte Klammer im globalen Bereich festgestellt. In den meisten Fällen wird dieser Fehler aufgrund eines falsch formatierten Funktionsheaders, einer falsch platzierten Deklaration oder eines fehlgeleiteten Semikolons verursacht. Stellen Sie zur Behebung dieses Problems sicher, dass die öffnende Klammer einem ordnungsgemäß formatierten Funktionsheader folgt und ihr weder eine Deklaration noch ein fehlgeleitetes Semikolon vorangeht.

Dieser Fehler kann auch von einer formalen C-Argumentliste im alten Stil verursacht werden. Gestalten Sie zur Behebung dieses Problems die Argumentliste um. Der moderne Stil sieht runde Klammern vor.

Im folgende Beispiel wird die C2447 generiert:

```
// C2447.cpp
int c;
{}       // C2447
```