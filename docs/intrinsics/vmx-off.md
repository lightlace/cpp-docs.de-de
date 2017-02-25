---
title: "__vmx_off | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_off"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMXOFF-Anweisung"
  - "__vmx_off (systemintern)"
ms.assetid: 78a32d46-9291-406c-b982-a550855aff18
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_off
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Deaktiviert Vorgang der Erweiterungen des virtuellen Computers \(VMX\) im Prozessor.  
  
## Syntax  
  
```  
void __vmx_off();  
```  
  
## Hinweise  
 Die `__vmx_off`\-Funktion ähnelt dem `VMXOFF` Computeranweisung.  Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen zur Suche für das Dokument „Intel\-Virtualisierungs\-technische Spezifikation für die Architektur, Intel IA\-32“ Belegnummer C97063 \-002 auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__vmx_off`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)