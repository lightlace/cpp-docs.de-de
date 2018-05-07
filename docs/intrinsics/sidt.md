---
title: __sidt | Microsoft Docs
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
ms.openlocfilehash: 29e41b0edd9b2a3da1046888f16a55e19f2d9f20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="sidt"></a>__sidt
**Microsoft-spezifisch**  
  
 Speichert den Wert des Interrupt Deskriptor Tabelle Registers (IDTR) in der angegebenen Speicheradresse.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `Destination`|Ein Zeiger auf die Speicheradresse, wo die IDTR gespeichert werden.|  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__sidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Die `__sidt` -Funktion ist gleichbedeutend mit der `SIDT` computeranweisung. Weitere Informationen zu suchen, für das Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set-Reference" auf der [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) Standort.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)