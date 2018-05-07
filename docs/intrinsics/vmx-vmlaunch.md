---
title: __vmx_vmlaunch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmlaunch
dev_langs:
- C++
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 926195aa8dc612d3972634f8140ce3fff753a48f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="vmxvmlaunch"></a>__vmx_vmlaunch
**Microsoft-spezifisch**  
  
 Platziert die aufrufende Anwendung in der VMX-Vorgang ohne Stamm Status (VM-enter) mit der aktuellen virtuellen Maschine Kontrollstruktur (VMCS).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|0|Der Vorgang wurde erfolgreich ausgeführt.|  
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|  
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Anwendung kann einen VM-enter-Vorgang ausführen, indem Sie entweder die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) oder [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion. Die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) Funktion kann verwendet werden, nur mit einer VMCS, deren Startstatus `Clear`, und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion kann verwendet werden, nur mit einer VMCS, deren Startstatus `Launched`. Verwenden Sie daher die [__vmx_vmclear](../intrinsics/vmx-vmclear.md) -Funktion zum Festlegen des Startstatus des einer VMCS auf `Clear`, und verwenden Sie dann die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion für die erste VM-enter-Vorgang und der [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion für alle nachfolgenden VM-enter-Operationen.  
  
 Die `__vmx_vmlaunch` -Funktion ist gleichbedeutend mit der `VMLAUNCH` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie für Weitere Informationen suchen, für das Dokument "Intel Virtualization technische Spezifikation für der IA-32 Intel Architecture" Dokumentnummer C97063-002 auf der [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmlaunch`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)