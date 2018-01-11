---
title: __svm_vmrun | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_vmrun
dev_langs: C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 000e798dce3fba367a8666d4b5c97bd25fd53253
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="svmvmrun"></a>__svm_vmrun
**Microsoft-spezifisch**  
  
 Startet die Ausführung der virtuellen Maschine Gast-Code, der den angegebenen virtuellen Computer-Kontrollblock (VMCB) entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `VmcbPhysicalAddress`|Die physische Adresse von der VMCB.|  
  
## <a name="remarks"></a>Hinweise  
 Die `__svm_vmrun` Funktion verwendet eine minimale Menge an Informationen in den VMCB beginnen Sie den VM-Gast-Code ausführen. Verwenden der [__svm_vmsave](../intrinsics/svm-vmsave.md) oder [__svm_vmload](../intrinsics/svm-vmload.md) funktioniert, wenn Sie weitere Informationen zu einem komplexen Unterbrechung zu verarbeiten oder wechseln Sie zu einem anderen Gast benötigen.  
  
 Die `__svm_vmrun` -Funktion ist gleichbedeutend mit der `VMRUN` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593, Revision 3.11 oder höher, auf die [AMD Corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_vmrun`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)