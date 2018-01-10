---
title: _InterlockedAddLargeStatistic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
dev_langs: C++
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d9e61abc6ac531fe489465b1d81e167bdde5242
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic
**Microsoft-spezifisch**  
  
 Führt eine ineinander greifende Addition, in der der erste Operand einer 64-Bit-Wert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in, out] `Addend`  
 Ein Zeiger auf den ersten Operanden für den Add-Vorgang. Der Wert, auf die gezeigt wird durch das Ergebnis der Addition ersetzt.  
  
 [in] `Value`  
 Der zweite Operand; der erste Operand hinzuzufügende Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Wert des zweiten Operanden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminterne Funktion ist nicht unteilbar, da er implementiert wurde, wie zwei separate von gesperrten Anweisungen. Ein atomic 64-Bit-Lesevorgang, die in einem anderen Thread während der Ausführung dieses systeminterne auftritt verursachen inkonsistent der gelesene Wert.  
  
 Diese Funktion verhält sich wie ein Hindernis für Lese-/ Schreibzugriff. Weitere Informationen finden Sie unter [ReadWriteBarrier](../intrinsics/readwritebarrier.md).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)