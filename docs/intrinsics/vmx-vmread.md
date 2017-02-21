---
title: "__vmx_vmread | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMREAD-Anweisung"
  - "__vmx_vmread intrinsic"
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Liest ein angegebenes Feld aus der aktuellen Kontrollstruktur des virtuellen Computers \(VMCS\) und den Speicherorten es am angegebenen Speicherort.  
  
## Syntax  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|\[in\] `Field`|Das VMCS\-Feld zum Lesen.|  
|\[in\] `FieldValue`|Ein Zeiger auf den Speicherort, dessen Wert aus dem gelesen VMCS\-Feld zum Speichern `Field` angegeben durch den Parameter.|  
  
## Rückgabewert  
  
|Wert|Bedeutung|  
|----------|---------------|  
|0|Der Vorgang war erfolgreich.|  
|1|Der Vorgang fehlgeschlagen ist mit dem erweiterten Status verfügbar in `VM-instruction error field` des aktuellen VMCS.|  
|2|Der Vorgang fehlgeschlagen ist, ohne den Status verfügbar.|  
  
## Hinweise  
 Die `__vmx_vmread`\-Funktion ähnelt dem `VMREAD` Computeranweisung.  Der Wert des `Field`\-Parameters ist ein codierter Feld Index, der in Intel\-Dokumentation beschrieben wird.  Weitere Informationen finden Sie unter „das Dokument gesucht Intel\-Virtualisierungs\-technische Spezifikation für die Architektur, Intel IA\-32“ Belegnummer C97063 \-002, [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) zu der Website, und klicken Sie dann im Anhang C dieses Dokuments.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmwrite](../intrinsics/vmx-vmwrite.md)