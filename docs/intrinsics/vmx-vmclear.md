---
title: "__vmx_vmclear"
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
  - "__vmx_vmclear"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMCLEAR-Anweisung"
  - "__vmx_vmclear intrinsic"
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmclear
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Initialisiert die angegebene Kontrollstruktur des virtuellen Computers \(VMCS\) und legt dessen Startzustand zu `Clear`.  
  
## Syntax  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|\[in\] `VmcsPhysicalAddress`|Ein Zeiger auf eine 64\-Bit\-Speicheradresse, die die physische Adresse des VMCS enthält, die gelöscht werden soll.|  
  
## Rückgabewert  
  
|Wert|Bedeutung|  
|----------|---------------|  
|0|Der Vorgang war erfolgreich.|  
|1|Der Vorgang fehlgeschlagen ist mit dem erweiterten Status verfügbar in `VM-instruction error field` des aktuellen VMCS.|  
|2|Der Vorgang fehlgeschlagen ist, ohne den Status verfügbar.|  
  
## Hinweise  
 Eine Anwendung kann einen VM\-ENTER\-Vorgang ausführen, indem sie entweder [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) oder [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)\-Funktion verwendet.  Die [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)\-Funktion kann nur mit einem VMCS verwendet werden, dessen Startzustand `Clear`ist, und die [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)\-Funktion kann nur mit einem VMCS verwendet werden, dessen Startzustand `Launched`ist.  Infolgedessen verwenden Sie die [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)\-Funktion, um den Startzustand eines VMCS zu `Clear`festzulegen.  Verwenden Sie die [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)\-Funktion für den ersten VM\-ENTER\-Vorgang und die [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)\-Funktion für folgende VM\-ENTER\-Vorgänge.  
  
 Die `__vmx_vmclear`\-Funktion ähnelt dem `VMCLEAR` Computeranweisung.  Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen zur Suche für das Dokument „Intel\-Virtualisierungs\-technische Spezifikation für die Architektur, Intel IA\-32“ Belegnummer C97063 \-002 auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)