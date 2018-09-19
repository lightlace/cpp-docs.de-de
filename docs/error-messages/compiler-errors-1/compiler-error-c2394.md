---
title: Compilerfehler C2394 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2394
dev_langs:
- C++
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfb1db7ab7cb1b44ff61d4cf6d5a22d5365da4b4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051684"
---
# <a name="compiler-error-c2394"></a>Compilerfehler C2394

'your_type' ": CLR oder WinRToperator ist ungültig. Mindestens ein Parameter muss einer der folgenden Typen sein: 'T^', 'T^%', 'T^&', wobei T = 'your_type'

Ein Operator in einer Windows-Runtime oder einem verwalteten Typen hatte nicht mindestens einen Parameter, dessen Typ mit dem Typen des Operatorrückgabewerts identisch ist.

Im folgenden Beispiel wird C2394 generiert:

```
// C2394.cpp
// compile with: /clr /c
ref struct Y {
   static Y^ operator -(int i, char c);   // C2394

   // OK
   static Y^ operator -(Y^ hY, char c);
   // or
   static Y^ operator -(int i, Y^& rhY);
};
```