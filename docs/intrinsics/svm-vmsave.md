---
title: "__svm_vmsave | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_vmsave"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMSAVE-Anweisung"
  - "__svm_vmsave (systemintern)"
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# __svm_vmsave
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Speichert eine Teilmenge des Funktionszustands der Zentraleinheit im angegebenen Kontrollblock des virtuellen Computers \(VMCB\).  
  
## Syntax  
  
```  
void __svm_vmsave(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|\[in\] `VmcbPhysicalAddress`|Die physische Adresse des VMCB.|  
  
## Hinweise  
 Die `__svm_vmsave`\-Funktion ähnelt dem `VMSAVE` Computeranweisung.  Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen zum Suchen nach „das Dokument manuell Volume 2 des Programmierers der Architektur\-AMD64: System\-Programmierung,“ Belegnummer 24593, Revision 3.11 oder höher, auf der Website [AMD Corporation](http://go.microsoft.com/fwlink/?LinkId=23746) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__svm_vmsave`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmrun](../intrinsics/svm-vmrun.md)   
 [\_\_svm\_vmload](../intrinsics/svm-vmload.md)