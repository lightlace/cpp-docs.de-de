---
title: "__vmx_vmresume | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmresume"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmresume (systemintern)"
  - "VMRESUME-Anweisung"
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# __vmx_vmresume
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Setzt einen VMX\-Vorgang ohne Stamm mithilfe der aktuellen Kontrollstruktur des virtuellen Computers \(Virtual Machine Control Structure, VMCS\) fort.  
  
## Syntax  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## Rückgabewert  
  
|Wert|Bedeutung|  
|----------|---------------|  
|0|Der Vorgang wurde erfolgreich ausgeführt.|  
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|  
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|  
  
## Hinweise  
 Eine Anwendung kann einen „VM\-enter“\-Vorgang mithilfe der [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)\- oder `__vmx_vmresume`\-Funktion ausführen. Die `__vmx_vmlaunch`\-Funktion kann nur mit einer VMCS verwendet werden, deren Startstatus `Clear` lautet, während die `__vmx_vmresume`\-Funktion nur mit einer VMCS verwendet werden kann, deren Startstatus `Launched` lautet. Verwenden Sie daher die [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)\-Funktion zum Festlegen des Startstatus einer VMCS auf `Clear`. Verwenden Sie dann die `__vmx_vmlaunch`\-Funktion für den ersten „VM\-enter“\-Vorgang und die `__vmx_vmresume`\-Funktion für nachfolgende „VM\-enter“\-Vorgänge.  
  
 Die `__vmx_vmresume`\-Funktion entspricht der `VMRESUME`\-Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen erhalten Sie, indem Sie nach dem PDF\-Dokument „Intel Virtualization Technical Specification for the IA\-32 Intel Architecture“ Dokumentnummer C97063\-002 auf der Website der [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) suchen.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)