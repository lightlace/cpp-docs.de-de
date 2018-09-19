---
title: Compilerfehler C3195 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3195
dev_langs:
- C++
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c299704b595ca6e6f6b81fb56ffad5534f81e6b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040595"
---
# <a name="compiler-error-c3195"></a>Compilerfehler C3195

"operator" : ist reserviert und kann nicht als Member einer Verweisklasse oder eines Werttyps verwendet werden. CLR- oder WinRT-Operatoren müssen mit dem Schlüsselwort "operator" definiert werden.

Der Compiler hat eine Operatordefinition gefunden, in der die Managed Extensions for C++-Syntax verwendet wird. Sie müssen die C++-Syntax für Operatoren verwenden.

Im folgenden Beispiel wird C3195 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```