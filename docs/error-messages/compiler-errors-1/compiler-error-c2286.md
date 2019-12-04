---
title: Compilerfehler C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 79697a17d322ae15a21e522efa7dfd5c2342f7a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759164"
---
# <a name="compiler-error-c2286"></a>Compilerfehler C2286

Zeiger auf Member der "Identifier"-Darstellung sind bereits auf "Vererbung" festgelegt-Deklaration wird ignoriert.

Für die-Klasse sind zwei verschiedene Pointer-to-Member-Darstellungen vorhanden.

Weitere Informationen finden Sie unter [Vererbungs Schlüsselwörter](../../cpp/inheritance-keywords.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2286 generiert:

```cpp
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```
