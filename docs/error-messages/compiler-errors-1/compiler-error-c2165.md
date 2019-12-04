---
title: Compilerfehler C2165
ms.date: 11/04/2016
f1_keywords:
- C2165
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
ms.openlocfilehash: 3bfaa07fa4524e5883b2744d5686e90fc9683016
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755680"
---
# <a name="compiler-error-c2165"></a>Compilerfehler C2165

'Schlüsselwort': Zeiger auf Daten können nicht geändert werden.

Das `__stdcall`-, `__cdecl`- oder `__fastcall` -Schlüsselwort versucht, einen Zeiger auf Daten zu ändern.

Im folgenden Beispiel wird C2165 generiert:

```cpp
// C2165.cpp
// compile with: /c
char __cdecl *p;   // C2165
char *p;   // OK
```
