---
title: Compilerwarnung (Stufe 1) C4399 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aedad6aed07a6056f74ad338037a7268c722627f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703719"
---
# <a name="compiler-warning-level-1-c4399"></a>Compilerwarnung (Stufe 1) C4399

> "*Symbol*": prozessspezifisch Symbol sollten nicht gekennzeichnet werden, mit von "__declspec(dllimport)" "beim Kompilieren mit/clr: pure

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird.

Daten über ein systemeigenes Image oder ein Bild mit einheitlichen und den CLR-Konstrukte können in einem reinen Image nicht importiert werden. Um diese Warnung zu beheben, kompilieren Sie mit **"/ CLR"** (nicht **/CLR: pure**) oder Löschen von `__declspec(dllimport)`.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4399 generiert.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```