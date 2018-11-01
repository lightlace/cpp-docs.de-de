---
title: Compilerfehler C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: e2b08ef3e46681147c4efd77cbffadb096bbfc16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590458"
---
# <a name="compiler-error-c2492"></a>Compilerfehler C2492

"*Variable*': Daten mit threadspeicherdauer dürfen keine Dll-Schnittstelle haben

Die Variable wird deklariert, mit der [Thread](../../cpp/thread.md) Attribut, und die DLL-Schnittstelle. Die Adresse der `thread` Variable ist nicht bis zur Laufzeit bekannt, damit nicht zu einer DLL-Import oder Export verknüpft werden.

Im folgende Beispiel wird die C2492 generiert:

```
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```