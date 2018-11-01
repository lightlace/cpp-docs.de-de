---
title: Compilerfehler C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: eb7b55f63e911f155c13e777e2e84ae7b587e9a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432668"
---
# <a name="compiler-error-c3353"></a>Compilerfehler C3353

'Delegat': Ein Delegat kann nur von einer globalen Funktion oder einer Memberfunktion eines verwalteten oder WinRT-Typs erstellt werden.

Delegaten, mit dem deklariert die [Delegieren](../../windows/delegate-cpp-component-extensions.md) Schlüsselwort kann nur im globalen Gültigkeitsbereich deklariert werden.

Im folgenden Beispiel wird C3353 generiert:

```
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```