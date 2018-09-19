---
title: Compilerwarnung (Stufe 1) C4167 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4167
dev_langs:
- C++
helpviewer_keywords:
- C4167
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c154a91c21bf0b35493bb8033e5453ef1c536267
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082182"
---
# <a name="compiler-warning-level-1-c4167"></a>Compilerwarnung (Stufe 1) C4167

Funktion: Nur als systeminterne Funktion verfügbar

Die **#pragma-Funktion** versucht zu erzwingen, dass der Compiler einen konventionellen Aufruf für eine Funktion verwendet, die in systeminterner Form verwendet werden muss. Das Pragma wird ignoriert.

Um diese Warnung zu vermeiden, entfernen Sie die **#pragma-Funhtion**.

## <a name="example"></a>Beispiel

```
// C4167.cpp
// compile with: /W1
#include <malloc.h>
#pragma function(_alloca )   // C4167: _alloca() is intrinsic only
int main(){}
```