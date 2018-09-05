---
title: __halt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee82433b45e89dd4f2f8039a9690d343723b96a6
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686671"
---
# <a name="halt"></a>__halt
**Microsoft-spezifisch**  
  
 Hält den Mikroprozessor, bis eine aktivierte Unterbrechung, einen nicht maskierbaren Interrupt (NMI) oder eine Zurücksetzung erfolgt.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __halt( void );  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__halt`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Die `__halt` -Funktion ist gleichbedeutend mit der `HLT` computeranweisung und steht nur im Kernelmodus ausgeführt. Weitere Informationen zu suchen, nach dem Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set Reference," auf die [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm) Standort.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)