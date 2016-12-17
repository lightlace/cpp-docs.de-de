---
title: "__svm_vmrun"
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
  - "__svm_vmrun"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_vmrun intrinsic"
  - "VMRUN-Anweisung"
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# __svm_vmrun
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Startet die Ausführung des Codes Gast des virtuellen Computers, der dem angegebenen Kontrollblock des virtuellen Computers \(VMCB\) entspricht.  
  
## Syntax  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|\[in\] `VmcbPhysicalAddress`|Die physische Adresse des VMCB.|  
  
## Hinweise  
 Die `__svm_vmrun`\-Funktion verwendet eine minimale Menge im VMCB beginnen den Gast Code des virtuellen Computers.  Verwenden Sie die [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md) oder [\_\_svm\_vmload](../intrinsics/svm-vmload.md)\-Funktion, wenn Sie weitere Informationen, um eine komplexe Unterbrechung behandeln benötigen oder in einem anderen Gast zu wechseln.  
  
 Die `__svm_vmrun`\-Funktion ähnelt dem `VMRUN` Computeranweisung.  Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen zum Suchen nach „das Dokument manuell Volume 2 des Programmierers der Architektur\-AMD64: System\-Programmierung,“ Belegnummer 24593, Revision 3.11 oder höher, auf der Website [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__svm_vmrun`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md)   
 [\_\_svm\_vmload](../intrinsics/svm-vmload.md)