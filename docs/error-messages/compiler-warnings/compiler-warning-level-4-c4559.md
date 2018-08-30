---
title: Compilerwarnung (Stufe 4) C4559 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4559
dev_langs:
- C++
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d5743b33f62aa954c3765b729ab5c0297b20e32
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195575"
---
# <a name="compiler-warning-level-4-c4559"></a>Compilerwarnung (Stufe 4) C4559

> "*Funktion*": Neudefinition; die Funktion Gewinne __declspec (*Modifizierer*)

## <a name="remarks"></a>Hinweise

Eine Funktion neu definiert wurde, oder erneut deklariert und die zweite Definition oder Deklaration hinzugefügt. eine **__declspec** Modifizierer (*Modifizierer*). Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, löschen Sie eine der Definitionen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4559 generiert:

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```