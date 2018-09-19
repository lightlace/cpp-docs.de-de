---
title: __debugbreak | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __debugbreak_cpp
- __debugbreak
dev_langs:
- C++
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9884cd8aec09bfcefaa8455457a3a4d3bb5b3d3d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219230"
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
|`__debugbreak`|X86, ARM, x64|\<intrin.h>|  
  
## <a name="remarks"></a>Hinweise  
 Die `__debugbreak` systeminterne Compilerfunktion ähnelt ["DebugBreak"](https://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), ist eine portable Win32-Methode, die einen Haltepunkt bewirkt.  
  
> [!NOTE]
>  Beim Kompilieren mit **"/ CLR"**, eine Funktion, `__debugbreak` in MSIL kompiliert wird. `asm int 3` bewirkt, dass eine Funktion in systemeigenem Code kompiliert wird. Weitere Informationen finden Sie unter [__asm](../assembler/inline/asm.md).  
  
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