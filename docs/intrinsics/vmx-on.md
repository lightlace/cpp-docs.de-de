---
title: "__vmx_on | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_on"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMXON-Anweisung"
  - "__vmx_on intrinsic"
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_on
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Aktiviert Vorgang der Erweiterungen des virtuellen Computers \(VMX\) im Prozessor.  
  
## Syntax  
  
```  
unsigned char __vmx_on(  
   unsigned __int64 *VmsSupportPhysicalAddress  
);  
```  
  
#### Parameter  
 \[in\] `VmsSupportPhysicalAddress`  
 Ein Zeiger auf eine 64\-Bit\-physischen Adresse, die zu einer Kontrollstruktur des virtuellen Computers \(VMCS\) zeigt.  
  
## Rückgabewert  
  
|Wert|Bedeutung|  
|----------|---------------|  
|0|Der Vorgang war erfolgreich.|  
|1|Der Vorgang fehlgeschlagen ist mit dem erweiterten Status verfügbar in `VM-instruction error field` des aktuellen VMCS.|  
|2|Der Vorgang fehlgeschlagen ist, ohne den Status verfügbar.|  
  
## Hinweise  
 Die `__vmx_on`\-Funktion entspricht dem `VMXON` Computeranweisung.  Diese Funktion unterstützt die Interaktion des Bildschirms des virtuellen Computers eines Hosts mit einem Betriebssystem Gast und ihren Anwendungen.  Weitere Informationen finden Sie für das Dokument „Intel\-Virtualisierungs\-technische Spezifikation der IA\-32 Architektur, Intel Belegnummer“ C97063 \-002 auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__vmx_on`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)