---
title: "__svm_clgi | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_clgi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLGI-Anweisung"
  - "__svm_clgi intrinsic"
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_clgi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Löscht die globale Unterbrechungsmarke.  
  
## Syntax  
  
```  
void __svm_clgi( void );  
```  
  
## Hinweise  
 Die `__svm_clgi`\-Funktion ähnelt dem `CLGI` Computeranweisung.  Die globale Unterbrechungsmarke bestimmt, ob der Mikroprozessor aufgrund von Unterbrechungen Ereignisse wie eine E\/A\-Komplettierung, eine Hardware temperatur warnung oder eine Ausnahme ignoriert, hinausschiebt oder behandelt.  
  
 Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen finden Sie im Artikel „, für das Dokument manuell Volume 2 des Programmierers der Architektur\-AMD64: System\-Programmierung,“ Belegnummer 24593, Revision 3.11 auf der Website [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__svm_clgi`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## BEENDEN Sie Microsoft\-Besonderen  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_stgi](../intrinsics/svm-stgi.md)