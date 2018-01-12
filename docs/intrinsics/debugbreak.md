---
title: __debugbreak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __debugbreak_cpp
- __debugbreak
dev_langs: C++
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07cac11754a8b5f242c38d5fd45d4c7f0707d69a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="debugbreak"></a>__debugbreak
**Microsoft-spezifisch**  
  
 Bewirkt, dass ein Haltepunkt im Code festgelegt wird, an dem der Benutzer zum Ausführen des Debuggers aufgefordert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __debugbreak();  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|Header|  
|---------------|------------------|------------|  
|`__debugbreak`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<INTRIN.h >|  
  
## <a name="remarks"></a>Hinweise  
 Die `__debugbreak` Compiler systeminterne, ähnlich wie ["DebugBreak"](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), ist eine portable Win32-Methode, um einen Haltepunkt bewirkt.  
  
> [!NOTE]
>  Beim Kompilieren mit **"/ CLR"**, eine Funktion, `__debugbreak` werden in MSIL kompiliert werden. `asm int 3` bewirkt, dass eine Funktion in systemeigenem Code kompiliert wird. Weitere Informationen finden Sie unter [__asm](../assembler/inline/asm.md).  
  
 Zum Beispiel:  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 ist vergleichbar mit:  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 auf einem x86-Computer.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)