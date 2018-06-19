---
title: Compilerfehler C3012 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d30a7fbb50a984c8cec6b45a0ab4759a0578de7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245452"
---
# <a name="compiler-error-c3012"></a>Compilerfehler C3012
  
> "*systeminterne*": systeminterne Funktion direkt innerhalb eines parallelen Bereichs ist nicht zulässig  
  
 Eine [systeminterne Compilerfunktion](../../intrinsics/compiler-intrinsics.md) ist in einem `omp parallel` Bereich nicht zulässig. Um dieses Problem zu beheben, verschieben Sie die Region mit systeminternen Funktionen oder nicht systeminternen Entsprechungen ersetzen.   
  
## <a name="example"></a>Beispiel  
  
 Im folgenden Beispiel wird C3012 generiert und zeigt eine Möglichkeit, sie diesen Fehler beheben:  
  
```cpp  
// C3012.cpp  
// compile with: /openmp  
#ifdef __cplusplus  
extern "C" {  
#endif  
void* _ReturnAddress();  
#ifdef __cplusplus  
}  
#endif  
  
int main()  
{  
   #pragma omp parallel  
   {  
      _ReturnAddress();   // C3012  
   }  
   _ReturnAddress();      // OK  
}  
```