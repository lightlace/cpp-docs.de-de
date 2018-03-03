---
title: Compilerfehler C2457 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2457
dev_langs:
- C++
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff89bb3635936ae0f797438d73f71adf1ef08de7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2457"></a>Compilerfehler C2457

> "*Makro*': das vordefinierte Makro kann nicht außerhalb eines Funktionsrumpfs angezeigt werden

Sie haben versucht, ein vordefiniertes Makro verwenden, z. B. [&#95; &#95; FUNCTION &#95; &#95; ](../../preprocessor/predefined-macros.md), in einem globalen Bereich.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2457 generiert und zeigt außerdem die richtige Verwendung:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```