---
title: "Systeminterne Funktionen „_InterlockedIncrement“ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedIncrement_acq"
  - "_InterlockedIncrement16_rel_cpp"
  - "_InterlockedIncrement16_cpp"
  - "_InterlockedIncrement64_rel"
  - "_InterlockedIncrement_rel"
  - "_InterlockedIncrement64_nf"
  - "_InterlockedIncrement16_acq_cpp"
  - "_InterlockedIncrement_rel_cpp"
  - "_InterlockedIncrement64"
  - "_InterlockedIncrement64_rel_cpp"
  - "_InterlockedIncrement16_nf"
  - "_InterlockedIncrement16_rel"
  - "_InterlockedIncrement16_acq"
  - "_InterlockedIncrement_nf"
  - "_InterlockedIncrement_acq_cpp"
  - "_InterlockedIncrement64_cpp"
  - "_InterlockedIncrement64_acq_cpp"
  - "_InterlockedIncrement"
  - "_InterlockedIncrement_cpp"
  - "_InterlockedIncrement64_acq"
  - "_InterlockedIncrement16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systeminterne Funktion „_InterlockedIncrement“"
  - "Systeminterne Funktion „_InterlockedIncrement_acq“"
  - "Systeminterne Funktion „_InterlockedIncrement_nf“"
  - "Systeminterne Funktion „_InterlockedIncrement_rel“"
  - "Systeminterne Funktion „_InterlockedIncrement16“"
  - "Systeminterne Funktion „_InterlockedIncrement16_acq“"
  - "Systeminterne Funktion „_InterlockedIncrement16_nf“"
  - "Systeminterne Funktion „_InterlockedIncrement16_rel“"
  - "Systeminterne Funktion „_InterlockedIncrement64“"
  - "Systeminterne Funktion „_InterlockedIncrement64_acq“"
  - "Systeminterne Funktion „_InterlockedIncrement64_nf“"
  - "Systeminterne Funktion „_InterlockedIncrement64_rel“"
  - "Systeminterne Funktion „InterlockedIncrement“"
  - "Systeminterne Funktion „InterlockedIncrement_acq“"
  - "Systeminterne Funktion „InterlockedIncrement_rel“"
  - "Systeminterne Funktion „InterlockedIncrement16“"
  - "Systeminterne Funktion „InterlockedIncrement64“"
  - "Systeminterne Funktion „InterlockedIncrement64_acq“"
  - "Systeminterne Funktion „InterlockedIncrement64_rel“"
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Systeminterne Funktionen „_InterlockedIncrement“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Stellt systeminterne Compiler\-Unterstützung für die Win32\-[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [InterlockedIncrement](http://msdn.microsoft.com/library/ms683614.aspx)\-Funktion bereit.  
  
## Syntax  
  
```  
long _InterlockedIncrement(  
   long * lpAddend  
);  
long _InterlockedIncrement_acq(  
   long * lpAddend  
);  
long _InterlockedIncrement_rel(  
   long * lpAddend  
);  
long _InterlockedIncrement_nf(  
   long * lpAddend  
);  
short _InterlockedIncrement16(  
   short * lpAddend  
);  
short _InterlockedIncrement16_acq(  
   short * lpAddend  
);  
short _InterlockedIncrement16_rel(  
   short * lpAddend  
);  
short _InterlockedIncrement16_nf (  
   short * lpAddend  
);  
__int64 _InterlockedIncrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedIncrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### Parameter  
 \[in, out\] `lpAddend`  
 Zeiger auf die zu erhöhende Variable.  
  
## Rückgabewert  
 Der Rückgabewert ist der resultierende erhöhte Wert.  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`_InterlockedIncrement`, `_InterlockedIncrement16`, `_InterlockedIncrement64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM|\<intrin.h\>|  
  
## Hinweise  
 Es gibt mehrere Varianten von `_InterlockedIncrement`, die sich basierend auf den beinhalteten Datentypen und in Abhängigkeit davon unterscheiden, ob prozessorspezifische Semantiken zum Abrufen bzw. Freigeben verwendet werden.  
  
 Während die `_InterlockedIncrement`\-Funktion mit 32\-Bit\-Ganzzahlwerten arbeitet, verwendet `_InterlockedIncrement16`16\-Bit\-Ganzzahlwerte und `_InterlockedIncrement64` 64\-Bit\-Ganzzahlwerte.  
  
 Verwenden Sie auf ARM\-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken abrufen und freigeben müssen, beispielsweise am Anfang und Ende eines kritischen Abschnitts.  Die systeminternen Funktionen mit dem Suffix `_nf` \(„keine Umgrenzung“\) fungieren nicht als Arbeitsspeicherbarriere.  
  
 Die Variable, auf die der `lpAddend`\-Parameter zeigt, muss an einer 32\-Bit\-Grenze ausgerichtet sein; andernfalls schlägt diese Funktion auf x86\-Multiprozessorsystemen und allen Nicht\-x86\-Systemen fehl.  Weitere Informationen finden Sie unter [ausrichten](../cpp/align-cpp.md).  
  
 Die Win32\-Funktion wird in `Wdm.h` oder `Ntddk.h` deklariert.  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## Beispiel  
 Ein Beispiel zur Verwendung von `_InterlockedIncrement` finden Sie unter [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)