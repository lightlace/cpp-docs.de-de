---
title: Compilerfehler C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: bd783d9510b1699b33f108a4ce8d8c491028b758
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541897"
---
# <a name="compiler-error-c3387"></a>Compilerfehler C3387

"Member": "__declspec(dllexport)" "/\__declspec(dllimport) nicht auf einen Member eines verwalteten oder WinRT-Typ angewendet werden

Die `dllimport` und [Dllexport](../../cpp/dllexport-dllimport.md) `__declspec` Modifizierer sind nicht zulässig für Member eines verwalteten oder Windows-Runtime-Typ.

Im folgenden Beispiel wird C3387 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3387a.cpp
// compile with: /clr /c
ref class X2 {
   void __declspec(dllexport) mf() {   // C3387
   // try the following line instead
   // void mf() {
   }
};
```