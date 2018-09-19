---
title: __sidt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __sidt
dev_langs:
- C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6731bb6a06f775c06ba16eb4885a3982d934f3cd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699868"
---
# <a name="sidt"></a>__sidt
**Microsoft-spezifisch**  
  
 Speichert den Wert des Interrupt-Deskriptor Tabelle Registers (IDTR) in der angegebenen Speicheradresse.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*Ziel*|[in] Ein Zeiger auf die Speicheradresse, wo die IDTR gespeichert werden.|  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__sidt`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Die `__sidt` -Funktion ist gleichbedeutend mit der `SIDT` computeranweisung. Weitere Informationen zu suchen, nach dem Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set Reference," auf die [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm) Standort.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)