---
title: _WriteBarrier | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _WriteBarrier
dev_langs: C++
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e619341e05d868b97d67fef068999c16fb2b4e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="writebarrier"></a>_WriteBarrier
**Microsoft-spezifisch**  
  
 Begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus neu anordnen können.  
  
> [!CAUTION]
>  Die systeminternen `_ReadBarrier`-, `_WriteBarrier`- und `_ReadWriteBarrier`-Compilerfunktionen und das `MemoryBarrier`-Makro sind veraltet und sollten nicht verwendet werden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [Atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) und [Std:: Atomic\<T >](../standard-library/atomic.md), die definiert werden, der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md). Für den Hardwarezugriff verwenden die [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) (Compileroption) zusammen mit den [volatile](../cpp/volatile-cpp.md) Schlüsselwort.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _WriteBarrier(void);  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_WriteBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Die systeminterne `_WriteBarrier`-Funktion begrenzt die Compileroptimierungen, die Speicherzugriffsvorgänge über den Punkt des Aufrufs hinaus entfernen oder neu anordnen können.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_ReadBarrier](../intrinsics/readbarrier.md)   
 [ReadWriteBarrier](../intrinsics/readwritebarrier.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)