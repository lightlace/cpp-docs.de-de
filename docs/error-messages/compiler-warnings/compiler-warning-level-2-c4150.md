---
title: Compilerwarnung (Stufe 2) C4150
ms.date: 11/04/2016
f1_keywords:
- C4150
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
ms.openlocfilehash: 5f55347dbe7843e67a3c6ef0ab83b91c8fa9d283
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052157"
---
# <a name="compiler-warning-level-2-c4150"></a>Compilerwarnung (Stufe 2) C4150

Löschen eines Zeigers auf den unvollständigen Typ "Typ"; kein Dekonstruktor aufgerufen

Der **Delete** -Operator wird aufgerufen, um einen Typ zu löschen, der deklariert, aber nicht definiert wurde, sodass der Compiler einen Dekonstruktor nicht finden kann.

Im folgenden Beispiel wird C4150 generiert:

```cpp
// C4150.cpp
// compile with: /W2
class  IncClass;

void NoDestruct( IncClass* pIncClass )
{
   delete pIncClass;
} // C4150, define class to resolve

int main()
{
}
```