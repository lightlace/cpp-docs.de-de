---
title: Compilerwarnung (Stufe 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 52e80340a5157e9350b6d4bbf3bcabea0487e089
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541255"
---
# <a name="compiler-warning-level-4-c4032"></a>Compilerwarnung (Stufe 4) C4032

der formale Parameter "Number" hat beim herauf Stufen einen anderen Typ.

Der Parametertyp ist aufgrund von Standard Aktionen nicht kompatibel mit dem Typ in einer vorherigen Deklaration.

Dies ist ein Fehler in ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) und eine Warnung unter Microsoft-Erweiterungen (/Ze).

## <a name="example"></a>Beispiel

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```