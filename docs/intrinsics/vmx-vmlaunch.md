---
title: "__vmx_vmlaunch"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmlaunch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMLAUNCH-Anweisung"
  - "__vmx_vmlaunch intrinsic"
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmlaunch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Platziert die aufrufende Anwendung VMX nicht im Zustand ROOT\-Vorgangs \(VMs\), gibt unter Verwendung der aktuellen Kontrollstruktur des virtuellen Computers \(VMCS\).  
  
## Syntax  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## Rückgabewert  
  
|Wert|Bedeutung|  
|----------|---------------|  
|0|Der Vorgang war erfolgreich.|  
|1|Der Vorgang fehlgeschlagen ist mit dem erweiterten Status verfügbar in `VM-instruction error field` des aktuellen VMCS.|  
|2|Der Vorgang fehlgeschlagen ist, ohne den Status verfügbar.|  
  
## Hinweise  
 Eine Anwendung kann einen VM\-ENTER\-Vorgang ausführen, indem sie entweder [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) oder [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)\-Funktion verwendet.  Die [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)\-Funktion kann nur mit einem VMCS verwendet werden, dessen Startzustand `Clear`ist, und die [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)\-Funktion kann nur mit einem VMCS verwendet werden, dessen Startzustand `Launched`ist.  Infolgedessen verwenden Sie die [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)\-Funktion, um den Startzustand eines VMCS zu `Clear`festzulegen, und verwenden Sie dann die [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)\-Funktion für den ersten VM\-ENTER\-Vorgang und die [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)\-Funktion für folgende VM\-ENTER\-Vorgänge.  
  
 Die `__vmx_vmlaunch`\-Funktion ähnelt dem `VMLAUNCH` Computeranweisung.  Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen zur Suche für das Dokument „Intel\-Virtualisierungs\-technische Spezifikation für die Architektur, Intel IA\-32“ Belegnummer C97063 \-002 auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__vmx_vmlaunch`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)