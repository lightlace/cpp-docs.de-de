---
title: "_stat Structure st_mode-Feldkonstanten"
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
  - "S_IFCHR"
  - "S_IFDIR"
  - "_S_IWRITE"
  - "S_IFMT"
  - "_S_IFDIR"
  - "_S_IREAD"
  - "S_IEXEC"
  - "_S_IEXEC"
  - "_S_IFMT"
  - "S_IWRITE"
  - "S_IFREG"
  - "S_IREAD"
  - "_S_IFCHR"
  - "_S_IFREG"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_S_IEXEC-Funktion"
  - "_S_IFCHR-Funktion"
  - "_S_IFDIR-Funktion"
  - "_S_IFMT-Funktion"
  - "_S_IFREG-Funktion"
  - "_S_IREAD-Konstante"
  - "_S_IWRITE-Konstante"
  - "S_IEXEC-Konstante"
  - "S_IFCHR-Konstante"
  - "S_IFDIR-Konstante"
  - "S_IFMT-Konstante"
  - "S_IFREG-Konstante"
  - "S_IREAD-Konstanten"
  - "S_IWRITE-Konstante"
  - "st_mode-Feldkonstanten"
  - "stat-Struktur"
  - "stat-Struktur, Konstanten"
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# _stat Structure st_mode-Feldkonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## Hinweise  
 Diese Konstanten werden verwendet, um auf dem Dateityp **st\_mode** Feld [\_stat Struktur](../c-runtime-library/standard-types.md) festzulegen.  
  
 Die Bitmaskenkonstanten sind unten beschrieben:  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_S_IFMT`|Dateitypmaske|  
|`_S_IFDIR`|Verzeichnis|  
|`_S_IFCHR`|Zeichen erforderlich \(gibt ein Gerät an, wenn von\)|  
|`_S_IFREG`|Regulär|  
|`_S_IREAD`|Leseberechtigung, Besitzer|  
|`_S_IWRITE`|Schreibberechtigungen, Besitzer|  
|`_S_IEXEC`|Ausführen\/Suchenberechtigung, Besitzer aus|  
  
## Siehe auch  
 [\_stat\- und \_wstat\-Funktionen](../c-runtime-library/reference/stat-functions.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [Standardtypen](../c-runtime-library/standard-types.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)