---
title: "__sidt"
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
  - "__sidt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sidt-Anweisung"
  - "__sidt (systemintern)"
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# __sidt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Speichert den Wert des deskriptor\-Tabellen Unterbrechungen \(registers IDTR\) an der angegebenen Speicheradresse.  
  
## Syntax  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|\[in\] `Destination`|Ein Zeiger auf die Speicheradresse, an der das IDTR gespeichert wird.|  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__sidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Die `__sidt`\-Funktion ähnelt dem `SIDT` Computeranweisung.  Weitere Informationen Suche nach dem Dokument, das Handbuch „des Intel\-Architektur\-Softwareentwicklers, Volume 2: Anweisungs\-festgelegter Verweis“ auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## BEENDEN Sie Microsoft\-Besonderen  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_lidt](../intrinsics/lidt.md)