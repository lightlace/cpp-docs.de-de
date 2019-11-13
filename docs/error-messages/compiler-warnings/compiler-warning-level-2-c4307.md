---
title: Compilerwarnung (Stufe 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: b5566bca22c328328a49e82268b96e8ec0fedc95
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052066"
---
# <a name="compiler-warning-level-2-c4307"></a>Compilerwarnung (Stufe 2) C4307

"Operator": ganzzahliger konstanter Überlauf

Der-Operator wird in einem Ausdruck verwendet, der dazu führt, dass eine ganzzahlige Konstante den zugeordneten Speicherplatz überlagert. Möglicherweise müssen Sie einen größeren Typ für die Konstante verwenden. Ein **int** -Wert mit Vorzeichen enthält einen kleineren Wert als ein `unsigned int`, da der **signierte int** -Wert ein Bit zur Darstellung des Zeichens verwendet.

Im folgenden Beispiel wird C4307 generiert:

```cpp
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```