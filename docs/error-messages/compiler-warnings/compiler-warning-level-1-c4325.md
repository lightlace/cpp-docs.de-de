---
title: "Compilerwarnung (Stufe 1) C4325 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4325"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4325"
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4325
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Attribute für Standardabschnitt '**   
 ***Abschnitt* ' werden ignoriert**  
  
 Die Attribute eines Standardabschnitts dürfen nicht geändert werden.  Beispiel:  
  
```  
#pragma section(".sdata", long)  
```  
  
 Dadurch würde der Standardabschnitt `.sdata` überschrieben, in dem der Datentyp **short** zusammen mit dem Datentyp **long** verwendet wird.  
  
 Im Folgenden die Standardabschnitte, deren Attribute nicht geändert werden dürfen:  
  
-   .data  
  
-   .sdata  
  
-   .bss  
  
-   .sbss  
  
-   .text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 Weitere Abschnitte können später hinzugefügt werden.  
  
## Siehe auch  
 [section](../../preprocessor/section.md)