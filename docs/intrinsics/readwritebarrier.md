---
title: "_ReadWriteBarrier"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_ReadWriteBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadWriteBarrier (systemintern)"
  - "ReadWriteBarrier (systemintern)"
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "corob"
manager: "ghogen"
---
# _ReadWriteBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Begrenzt die Compileroptimierungen, die Speicherzugriffe über den Punkt des Aufrufs hinaus neu anordnen können.  
  
> [!CAUTION]
>  Die systeminternen `_ReadBarrier`\-, `_WriteBarrier`\- und `_ReadWriteBarrier`\-Compilerfunktionen und das `MemoryBarrier`\-Makro sind veraltet und sollten nicht verwendet werden.  Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) und [std::atomic\<T\>](../standard-library/atomic.md), die in der [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md) definiert sind.  Verwenden Sie für den Hardwarezugriff die [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)\-Compileroption zusammen mit dem [volatile](../cpp/volatile-cpp.md)\-Schlüsselwort.  
  
## Syntax  
  
```  
void _ReadWriteBarrier(void);  
```  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_ReadWriteBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Die systeminterne `_ReadWriteBarrier`\-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffe über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [\_ReadBarrier](../intrinsics/readbarrier.md)   
 [\_WriteBarrier](../intrinsics/writebarrier.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)