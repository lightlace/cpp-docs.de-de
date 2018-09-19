---
title: Compilerwarnung (Stufe 3) C4161 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4161
dev_langs:
- C++
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d279822d823ffb8efcaf08ff3f64cd9d82d0a44
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220557"
---
# <a name="compiler-warning-level-3-c4161"></a>Compilerwarnung (Stufe 3) C4161

> #<a name="pragma-pragmapop--more-pops-than-pushes"></a>Pragma *Pragma*(Namespacebereiche...): mehr POP-als Push-Vorgänge

## <a name="remarks"></a>Hinweise

Da der Quellcode, die einen POP-Vorgang mehr als Push-Vorgänge für das Pragma enthält *Pragma*, der Stapel Verhalten sich womöglich nicht wie erwartet. Um die Warnung zu vermeiden, achten Sie darauf, dass die Anzahl der pop-Vorgänge die der push-Vorgänge nicht überschreitet.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4161 generiert:

```cpp
// C4161.cpp
// compile with: /W3 /LD
#pragma pack(push, id)
#pragma pack(pop, id)
#pragma pack(pop, id)   // C4161, an extra pop

#pragma bss_seg(".my_data1")
int j;

#pragma bss_seg(push, stack1, ".my_data2")
int l;

#pragma bss_seg(pop, stack1)
int m;

#pragma bss_seg(pop, stack1)   // C4161
```