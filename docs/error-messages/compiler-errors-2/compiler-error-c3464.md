---
title: Compilerfehler C3464 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3464
dev_langs:
- C++
helpviewer_keywords:
- C3464
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05322479c076bbb929b6c742fdd379414a263376
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096579"
---
# <a name="compiler-error-c3464"></a>Compilerfehler C3464

"Typ" Ein geschachtelter Typ kann nicht weitergeleitet werden.

Weiterleiten von Typen funktioniert nicht bei geschachtelten Typen.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```
// C3464.cpp
// compile with: /LD /clr
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3464 generiert:

```
// C3464_b.cpp
// compile with: /clr /c
#using "C3464.dll"
[assembly:TypeForwardedTo(R::N::typeid)];   // C3464
[assembly:TypeForwardedTo(R::typeid)];   // OK
```