---
title: _InterlockedAddLargeStatistic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 602cfb415c17c9e57d9fc1e932777cd1929e5f40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331396"
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