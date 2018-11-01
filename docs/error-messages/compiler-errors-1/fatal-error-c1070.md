---
title: Schwerwiegender Fehler C1070
ms.date: 11/04/2016
f1_keywords:
- C1070
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
ms.openlocfilehash: 7e156a230ce9550b65d1b8775947fc7294c15377
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445018"
---
# <a name="fatal-error-c1070"></a>Schwerwiegender Fehler C1070

Fehlende Zuordnung von #if und #endif in Datei "Dateiname"

Einer `#if`-, `#ifdef`- oder `#ifndef` -Direktive fehlt das entsprechende `#endif`.

Im folgenden Beispiel wird C1070 generiert:

```
// C1070.cpp
#define TEST

#ifdef TEST

#ifdef TEST
#endif
// C1070
```

Mögliche Lösung:

```
// C1070b.cpp
// compile with: /c
#define TEST

#ifdef TEST
#endif

#ifdef TEST
#endif
```