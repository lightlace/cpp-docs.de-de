---
title: "__outbyte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__outbyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out-Anweisung"
  - "__outbyte intrinsic"
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __outbyte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `out`\-Anweisung, die 1 Byte sendet, das von der `Data` E\/A\-Port angegeben wird, der durch `Port`angegeben wird.  
  
## Syntax  
  
```  
void __outbyte(   
   unsigned short Port,   
   unsigned char Data   
);  
```  
  
#### Parameter  
 \[in\] `Port`  
 Der Anschluss, um die Daten zu senden.  
  
 \[in\] `Data`  
 Das Byte, werden ausgesendet den angegebenen Anschluss.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__outbyte`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)