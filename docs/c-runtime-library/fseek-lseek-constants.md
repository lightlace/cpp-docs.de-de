---
title: "fseek- und _lseek-Konstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SEEK_END"
  - "SEEK_SET"
  - "SEEK_CUR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SEEK_CUR-Konstante"
  - "SEEK_END-Konstante"
  - "SEEK_SET-Konstante"
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fseek- und _lseek-Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <stdio.h>  
  
```  
  
## Hinweise  
 Das *Ursprungsargument* gibt die Anfangsposition an und kann eine der folgenden Manifestkonstanten sein:  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`SEEK_END`|Dateiende|  
|`SEEK_CUR`|Aktuelle Position des Dateizeigers|  
|`SEEK_SET`|Anfang der Datei|  
  
## Siehe auch  
 [fseek, \_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)