---
title: __vmx_vmptrst | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __vmx_vmptrst
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a08626cd6238df51ee149cc7bf8d873b993fb95e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="vmxvmptrst"></a>__vmx_vmptrst
**Microsoft-spezifisch**  
  
 Speichert die Zeiger auf die aktuelle VM-Steuerelement-Struktur (VMCS) an der angegebenen Adresse an.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __vmx_vmptrst(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] *`VmcsPhysicalAddress`  
 Die Adresse, in der aktuellen VMCS Zeiger gespeichert ist.  
  
## <a name="remarks"></a>Hinweise  
 Der VMCS-Zeiger ist eine physische 64-Bit-Adresse.  
  
 Die `__vmx_vmptrst` -Funktion ist gleichbedeutend mit der `VMPTRST` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie für Weitere Informationen suchen, für das Dokument "Intel Virtualization technische Spezifikation für der IA-32 Intel Architecture" Dokumentnummer C97063-002 auf der [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmptrst`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)