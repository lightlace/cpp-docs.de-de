---
title: "Dateiberechtigungskonstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_S_IWRITE"
  - "_S_IREAD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_S_IREAD-Konstante"
  - "_S_IWRITE-Konstante"
  - "Konstanten [C++], Dateiattribute"
  - "Dateiberechtigungen [C++]"
  - "S_IREAD-Konstanten"
  - "S_IWRITE-Konstante"
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Dateiberechtigungskonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## Hinweise  
 Eine dieser Konstanten ist erforderlich, wenn `_O_CREAT` \(`_open`, `_sopen`\) angegeben wurde.  
  
 Das Argument `pmode` gibt die Berechtigungseinstellungen der Datei wie folgt an.  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_S_IREAD`|Lesen zulässig|  
|`_S_IWRITE`|Schreiben zulässig|  
|`_S_IREAD`  &#124; `_S_IWRITE`|Lesen und Schreiben zulässig|  
  
 Bei Verwendung als das Argument `pmode` für `_umask`, legt die Konstante Manifest die Berechtigungseinstellung, wie folgt fest.  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_S_IREAD`|Schreiben nicht zulässig \(Datei ist schreibgeschützt\)|  
|`_S_IWRITE`|Lesen nicht zulässig ist lesegeschützt \(Datei\)|  
|`_S_IREAD`  &#124; `_S_IWRITE`|Weder Lesen noch Schreiben zulässig|  
  
## Siehe auch  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_umask](../c-runtime-library/reference/umask.md)   
 [Standardtypen](../c-runtime-library/standard-types.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)