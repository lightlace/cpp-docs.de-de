---
title: Compilerfehler C2447 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2447
dev_langs:
- C++
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9cc18c8e6ffb31de062957e16f6f3a6573379ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035135"
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