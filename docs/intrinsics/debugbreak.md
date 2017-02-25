---
title: "__debugbreak | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__debugbreak_cpp"
  - "__debugbreak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__debugbreak-systemintern"
  - "Haltepunkte, __debugbreak-systemintern"
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# __debugbreak
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Bewirkt, dass ein Haltepunkt im Code festgelegt wird, an dem der Benutzer zum Ausführen des Debuggers aufgefordert wird.  
  
## Syntax  
  
```  
void __debugbreak();  
```  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`__debugbreak`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
  
## Hinweise  
 Die systeminterne Compilerfunktion `__debugbreak`, die [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx) ähnelt, ist eine portable Win32\-Methode, die einen Haltepunkt bewirkt.  
  
> [!NOTE]
>  Beim Kompilieren mit **\/clr** wird eine Funktion, die `__debugbreak` enthält, in MSIL kompiliert.  `asm int 3` bewirkt, dass eine Funktion in systemeigenem Code kompiliert wird.  Weitere Informationen finden Sie unter [\_\_asm](../assembler/inline/asm.md).  
  
 Beispiel:  
  
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
  
 auf einem x86\-Computer.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)