---
title: "_ReadBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReadBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadBarrier (systemintern)"
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _ReadBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus neu anordnen können.  
  
> [!CAUTION]
>  Die systeminternen `_ReadBarrier`\-, `_WriteBarrier`\- und `_ReadWriteBarrier`\-Compilerfunktionen und das `MemoryBarrier`\-Makro sind veraltet und sollten nicht verwendet werden.  Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) und [std::atomic\<T\>](../standard-library/atomic.md), die in der [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md) definiert sind.  Verwenden Sie für den Hardwarezugriff die [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)\-Compileroption zusammen mit dem [volatile](../cpp/volatile-cpp.md)\-Schlüsselwort.  
  
## Syntax  
  
```  
void _ReadBarrier(void);  
```  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_ReadBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Die systeminterne `_ReadBarrier`\-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)