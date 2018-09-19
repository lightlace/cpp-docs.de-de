---
title: __vmx_vmptrst | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrst
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e879726f9ef3ad65dabd00056ddb859c72dd039e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679566"
---
# <a name="vmxvmptrst"></a>__vmx_vmptrst
**Microsoft-spezifisch**  
  
 Speichert den Zeiger auf die aktuelle VM-Steuerelement-Struktur (VMCS) an der angegebenen Adresse an.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __vmx_vmptrst(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] *`VmcsPhysicalAddress`  
 Die Adresse, wo der Zeiger für den aktuelle VMCS gespeichert werden.  
  
## <a name="remarks"></a>Hinweise  
 Der Zeiger VMCS ist eine physische 64-Bit-Adresse.  
  
 Die `__vmx_vmptrst` -Funktion ist gleichbedeutend mit der `VMPTRST` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmptrst`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)