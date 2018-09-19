---
title: __vmx_vmptrld | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrld
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd04350df17b6d2dfed65526d0f7681c314f07f8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682619"
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld
**Microsoft-spezifisch**  
  
 Lädt den Zeiger auf die aktuellen VM-Steuerelement-Struktur (VMCS) aus der angegebenen Adresse an.  
  
## <a name="syntax"></a>Syntax  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] *`VmcsPhysicalAddress`  
 Die Adresse, wo der Zeiger VMCS gespeichert werden.  
  
## <a name="return-value"></a>Rückgabewert  
 0  
 Der Vorgang wurde erfolgreich ausgeführt.  
  
 1  
 Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.  
  
 2  
 Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.  
  
## <a name="remarks"></a>Hinweise  
 Der Zeiger VMCS ist eine physische 64-Bit-Adresse.  
  
 Die `__vmx_vmptrld` -Funktion ist gleichbedeutend mit der `VMPTRLD` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmptrld`|x64|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)