---
title: ReadWriteBarrier | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _ReadWriteBarrier
dev_langs: C++
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 50f58a23f1e2f0fde4a21a4eba64795c8de97629
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="readwritebarrier"></a>_ReadWriteBarrier
**Microsoft-spezifisch**  
  
 Begrenzt die Compileroptimierungen, die Speicherzugriffe über den Punkt des Aufrufs hinaus neu anordnen können.  
  
> [!CAUTION]
>  Die systeminternen `_ReadBarrier`-, `_WriteBarrier`- und `_ReadWriteBarrier`-Compilerfunktionen und das `MemoryBarrier`-Makro sind veraltet und sollten nicht verwendet werden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [Atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) und [Std:: Atomic\<T >](../standard-library/atomic.md), die definiert werden, der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md). Für den Hardwarezugriff verwenden die [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) (Compileroption) zusammen mit den [volatile](../cpp/volatile-cpp.md) Schlüsselwort.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _ReadWriteBarrier(void);  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_ReadWriteBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Die systeminterne `_ReadWriteBarrier`-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffe über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_ReadBarrier](../intrinsics/readbarrier.md)   
 [_WriteBarrier](../intrinsics/writebarrier.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)