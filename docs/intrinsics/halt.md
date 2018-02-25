---
title: __halt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __halt
- __halt_cpp
dev_langs:
- C++
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d2d3a530fe5e300c59cfd9ffa1d509b3b41b0f2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="halt"></a>__halt
**Microsoft-spezifisch**  
  
 Mikroprozessors angehalten, bis aktiviert Interrupt, einen nicht maskierbaren Interrupt (NMI) oder eine Zurücksetzung auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __halt( void );  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__halt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Die `__halt` -Funktion ist gleichbedeutend mit dem `HLT` computeranweisung und ist nur im Kernelmodus verfügbar. Weitere Informationen zu suchen, für das Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set-Reference" auf der [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) Standort.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)