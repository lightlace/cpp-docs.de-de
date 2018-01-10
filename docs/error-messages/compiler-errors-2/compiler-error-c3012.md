---
title: Compilerfehler C3012 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3012
dev_langs: C++
helpviewer_keywords: C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32c12397339f861b71fe41566f29fd1a8929b66e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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