---
title: __vmx_vmclear | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __vmx_vmclear
dev_langs:
- C++
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 323fcf37ee9ecc9e62abe5d6fdc30944e58862f8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="vmxvmclear"></a>__vmx_vmclear
**Microsoft-spezifisch**  
  
 Initialisiert den angegebenen virtuellen Computer Kontrollstruktur (VMCS) und legt seine Startstatus auf `Clear`.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `VmcsPhysicalAddress`|Ein Zeiger auf einen 64-Bit-Speicherbereich, der die physische Adresse eines der VMCS löschen enthält.|  
  
## <a name="return-value"></a>Rückgabewert  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|0|Der Vorgang wurde erfolgreich ausgeführt.|  
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|  
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Anwendung kann einen VM-enter-Vorgang ausführen, indem Sie entweder die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) oder [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion. Die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) Funktion kann verwendet werden, nur mit einer VMCS, deren Startstatus `Clear`, und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion kann verwendet werden, nur mit einer VMCS, deren Startstatus `Launched`. Verwenden Sie daher die [__vmx_vmclear](../intrinsics/vmx-vmclear.md) -Funktion zum Festlegen des Startstatus des einer VMCS auf `Clear`. Verwenden der [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion für die erste VM-enter-Vorgang und der [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion für alle nachfolgenden VM-enter-Operationen.  
  
 Die `__vmx_vmclear` -Funktion ist gleichbedeutend mit der `VMCLEAR` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie für Weitere Informationen suchen, für das Dokument "Intel Virtualization technische Spezifikation für der IA-32 Intel Architecture" Dokumentnummer C97063-002 auf der [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)