---
title: Compilerfehler C3152 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3152
dev_langs:
- C++
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 975ce5a948305f5b2538496ddef34e18bb6db63c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079686"
---
# <a name="compiler-error-c3152"></a>Compilerfehler C3152

'construct' : 'keyword' kann nur auf eine Klasse, Struktur oder virtuelle Memberfunktion angewendet werden.

Bestimmte Schlüsselwörter können nur auf eine C++-Klasse angewendet werden.

Im folgenden Beispiel wird C3152 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3152.cpp
// compile with: /clr /c
ref class C {
   int (*pfn)() sealed;   // C3152
   virtual int g() sealed;   // OK
};
```
