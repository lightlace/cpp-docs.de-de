---
title: __sidt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __sidt
dev_langs: C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c952c23af6e1695ca9032e0687334c4ebb881a1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 Die `__sidt` -Funktion ist gleichbedeutend mit der `SIDT` computeranweisung. Weitere Informationen zu suchen, für das Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set-Reference" auf der [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) Standort.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)