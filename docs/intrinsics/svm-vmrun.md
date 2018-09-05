---
title: __svm_vmrun | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmrun
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 086fbbc2a25c4af2b09f40d83ac0b20399860ca1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679805"
---
# <a name="svmvmrun"></a>__svm_vmrun
**Microsoft-spezifisch**  
  
 Startet die Ausführung der VM-Gast-Code, der die den angegebenen virtuellen Computer-Kontrollblock (VMCB) entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `VmcbPhysicalAddress`|Die physische Adresse der VMCB.|  
  
## <a name="remarks"></a>Hinweise  
 Die `__svm_vmrun` Funktion verwendet eine minimale Menge an Informationen in den VMCB, um zu beginnen, den VM-Gast-Code ausführen. Verwenden der [__svm_vmsave](../intrinsics/svm-vmsave.md) oder [__svm_vmload](../intrinsics/svm-vmload.md) ausgeführt werden, wenn Sie weitere Informationen zu einem komplexen Unterbrechung zu verarbeiten oder wechseln Sie zu einem anderen Gast benötigen.  
  
 Die `__svm_vmrun` -Funktion ist gleichbedeutend mit der `VMRUN` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593, Version 3.11 oder höher, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_vmrun`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)