---
title: "__svm_skinit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_skinit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SKINIT-Anweisung"
  - "__svm_skinit (systemintern)"
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_skinit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Initiiert das Laden der nachweislich sicheren Software, z. B. einem Bildschirm des virtuellen Computers.  
  
## Syntax  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`SLB`|Die 32\-Bit\-physische Adresse eines Bytewerts 64K speichern Ladeprogramm\-Block \(SLB\).|  
  
## Hinweise  
 Die `__svm_skinit`\-Funktion ähnelt dem `SKINIT` Computeranweisung.  Diese Funktion ist Teil eines Sicherheitssystems, der den Prozessor und Trusted Platform Module \(TPM\) verwendet wird, um die vertrauenswürdige Software zu untersuchen und zu laden, die über einen sicheren SK \(kernel\) aufgerufen wird.  Ein Bildschirm des virtuellen Computers ist ein Beispiel für einen sicheren kernels.  Das Sicherheitssystem überprüft das Programm Komponenten, die während des Prozesses Initialisierung geladen und schützt Komponenten von der Bearbeitung von Timeouts, Geräten oder Zugriff auf ein anderes Programm, wenn der Computer mit mehreren Prozessoren ein.  
  
 Der `SLB`\-Parameter gibt die physische Adresse eines Speicherblocks 64K an, der den *sicheren Ladeprogramm\-Block* SLB \(\) aufgerufen wird.  Das SLB enthält ein Programm, das das sichere Ladeprogramm aufgerufen wird, das die Betriebsumgebung für den Computer einrichtet, und lädt anschließend den Sicherheitsanforderungen kernel.  
  
 Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen zum Suchen nach „das Dokument manuell Volume 2 des Programmierers der Architektur\-AMD64: System\-Programmierung,“ Belegnummer 24593, Revision 3.11 auf der Website [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__svm_skinit`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)