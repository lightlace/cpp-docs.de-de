---
title: Compilerwarnung (Stufe 1) C4392 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4392
dev_langs:
- C++
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b64159737b9423f3d9ea55489eb28c20a2162d14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281257"
---
# <a name="compiler-warning-level-1-c4392"></a>Compilerwarnung (Stufe 1) C4392
"Signature": falsche Anzahl von Argumenten für die systeminterne Funktion erwartet 'Zahl'-Argumente  
  
 Eine Funktionsdeklaration für eine systeminterne Compilerfunktion hatte die falsche Anzahl von Argumenten. Das resultierende Image kann nicht ordnungsgemäß ausgeführt.  
  
 Um diese Warnung zu beheben, korrigieren Sie die Deklaration oder löschen Sie die Deklaration und einfach #include die entsprechende Headerdatei.  
  
 Im folgenden Beispiel wird C4392 generiert:  
  
```  
// C4392.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_stream_pd(double *dp);   // C4392  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```