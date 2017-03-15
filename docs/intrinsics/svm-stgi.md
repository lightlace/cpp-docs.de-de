---
title: "__svm_stgi | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_stgi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_stgi intrinsic"
  - "STGI-Anweisung"
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_stgi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Legt die globale Unterbrechungsmarke fest.  
  
## Syntax  
  
```  
void __svm_stgi(void);  
```  
  
## Hinweise  
 Die `__svm_stgi`\-Funktion ähnelt dem `STGI` Computeranweisung.  Die globale Unterbrechungsmarke bestimmt, ob der Mikroprozessor aufgrund von Unterbrechungen Ereignisse wie eine E\/A\-Komplettierung, eine Hardware temperatur warnung oder eine Ausnahme ignoriert, hinausschiebt oder behandelt.  
  
 Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen finden Sie im Artikel „, für das Dokument manuell Volume 2 des Programmierers der Architektur\-AMD64: System\-Programmierung,“ Belegnummer 24593, Revision 3.11 auf der Website [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__svm_stgi`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_clgi](../intrinsics/svm-clgi.md)