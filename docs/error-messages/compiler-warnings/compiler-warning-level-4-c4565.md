---
title: Compilerwarnung (Stufe 4) C4565 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4565
dev_langs:
- C++
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c25f2f1fc16c6d45a7d1eddec8d3efe62db142f2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211261"
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