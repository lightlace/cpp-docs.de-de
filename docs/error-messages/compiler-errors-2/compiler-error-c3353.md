---
title: Compilerfehler C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: c38642d7abd4f2fd50792c548c9a5521b2da10ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402644"
---
# <a name="compiler-error-c3353"></a>Compilerfehler C3353

'Delegat': Ein Delegat kann nur von einer globalen Funktion oder einer Memberfunktion eines verwalteten oder WinRT-Typs erstellt werden.

Delegaten, mit dem deklariert die [Delegieren](../../extensions/delegate-cpp-component-extensions.md) Schlüsselwort kann nur im globalen Gültigkeitsbereich deklariert werden.

Im folgenden Beispiel wird C3353 generiert:

```
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```