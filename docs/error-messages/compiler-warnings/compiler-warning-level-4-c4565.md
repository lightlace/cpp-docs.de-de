---
title: Compilerwarnung (Stufe 4) C4565
ms.date: 08/27/2018
f1_keywords:
- C4565
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
ms.openlocfilehash: b655dcfb456d32e45833e89e5a48926ad70d1d9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220480"
---
# <a name="compiler-warning-level-4-c4565"></a>Compilerwarnung (Stufe 4) C4565

> "*Funktion*": Neudefinition; das Symbol wurde zuvor mit __declspec deklariert (*Modifizierer*)

## <a name="remarks"></a>Hinweise

Ein Symbol wurde neu definiert oder erneut deklariert und die zweite Definition oder Deklaration, im Gegensatz zu den ersten Definition oder Deklaration keine `__declspec` Modifizierer (*Modifizierer*). Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, löschen Sie eine der Definitionen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4565 generiert:

```cpp
// C4565.cpp
// compile with: /W4 /LD
__declspec(noalias) void f();
void f();   // C4565
```