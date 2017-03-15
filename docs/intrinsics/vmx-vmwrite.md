---
title: "__vmx_vmwrite | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmwrite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmwrite intrinsic"
  - "VMWRITE-Anweisung"
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmwrite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Schreibt den angegebenen Wert in den angegebenen Feld in der aktuellen Kontrollstruktur des virtuellen Computers \(VMCS\).  
  
## Syntax  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|\[in\] `Field`|Das zu schreibende VMCS\-Feld.|  
|\[in\] `FieldValue`|Der zum VMCS\-Feld zu schreibende Wert.|  
  
## Rückgabewert  
 0  
 Der Vorgang war erfolgreich.  
  
 1  
 Der Vorgang fehlgeschlagen ist mit dem erweiterten Status verfügbar in `VM-instruction error field` des aktuellen VMCS.  
  
 2  
 Der Vorgang fehlgeschlagen ist, ohne den Status verfügbar.  
  
## Hinweise  
 Die `__vmx_vmwrite`\-Funktion ähnelt dem `VMWRITE` Computeranweisung.  Der Wert des `Field`\-Parameters ist ein codierter Feld Index, der in Intel\-Dokumentation beschrieben wird.  Weitere Informationen finden Sie unter „das Dokument gesucht Intel\-Virtualisierungs\-technische Spezifikation für die Architektur, Intel IA\-32“ Belegnummer C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) zu der Website, und klicken Sie dann auf Anhang C dieses Dokuments.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmread](../intrinsics/vmx-vmread.md)