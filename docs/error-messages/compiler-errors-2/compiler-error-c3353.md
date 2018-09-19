---
title: Compilerfehler C3353 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63316a5a74c3981ec0f68d949eba654f8d6bbfef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110197"
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