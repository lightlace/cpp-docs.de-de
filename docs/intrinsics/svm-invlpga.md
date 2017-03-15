---
title: "__svm_invlpga | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_invlpga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_invlpga (systemintern)"
  - "INVLPGA-Anweisung"
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_invlpga
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Macht den Eintrag neben Computerübersetzungs Adressabbildungs im Puffer.  Parameter geben den virtuellen Adressraum und Adressen\- Bezeichner der Seite an, die ungültig zu machen.  
  
## Syntax  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|\[in\] `Va`|Die virtuelle Adresse der Seite ungültig zu machen.|  
|\[in\] `ASID`|Der Adressraum \(Programmbezeichner\) ASID der Seite ungültig zu machen.|  
  
## Hinweise  
 Die `__svm_invlpga`\-Funktion ähnelt dem `INVLPGA` Computeranweisung.  Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen zum Suchen nach „das Dokument manuell Volume 2 des Programmierers der Architektur\-AMD64: System\-Programmierung,“ Belegnummer 24593, Revision 3.11 auf der Website [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__svm_invlpga`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)