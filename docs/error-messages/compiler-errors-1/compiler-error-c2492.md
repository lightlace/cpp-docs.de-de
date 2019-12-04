---
title: Compilerfehler C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: fd52b434f86bdc93124c6005bbf7fadad3cb56b2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757058"
---
# <a name="compiler-error-c2492"></a>Compilerfehler C2492

"*Variable*": Daten mit Thread Speicherdauer dürfen keine DLL-Schnittstelle aufweisen.

Die Variable wird mit dem [Thread](../../cpp/thread.md) -Attribut und mit der DLL-Schnittstelle deklariert. Die Adresse der `thread` Variablen ist erst zur Laufzeit bekannt, sodass Sie nicht mit einem DLL-Import oder-Export verknüpft werden kann.

Im folgenden Beispiel wird C2492 generiert:

```cpp
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```
