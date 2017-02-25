---
title: "Freigeben von Konstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SH_DENYNO"
  - "_SH_DENYRD"
  - "_SH_DENYRW"
  - "_SH_DENYWR"
  - "_SH_COMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SH_COMPAT-Konstante"
  - "_SH_DENYNO-Konstante"
  - "_SH_DENYRD-Konstante"
  - "_SH_DENYRW-Konstante"
  - "_SH_DENYWR-Konstante"
  - "SH_COMPAT-Konstante"
  - "SH_DENYNO-Konstante"
  - "SH_DENYRD-Konstante"
  - "SH_DENYRW-Konstante"
  - "SH_DENYWR-Konstante"
  - "Freigeben von Konstanten"
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Freigeben von Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Konstanten für Filesharing\- Modi.  
  
## Syntax  
  
```  
  
#include <share.h>  
  
```  
  
## Hinweise  
 Das *shflag*\-Argument bestimmt den Freigabenmodus, der aus mindestens Manifestkonstanten besteht.  Diese können mit den *oflag*\-Argumenten kombiniert werden \(siehe [Datei\-Konstanten](../c-runtime-library/file-constants.md)\).  
  
 In der folgenden Tabelle werden Konstanten und ihre Bedeutung auf:  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_SH_DENYRW`|Verweigert Lese\- und Schreibzugriff auf die Datei|  
|`_SH_DENYWR`|Verweigert Schreibzugriff auf die Datei|  
|`_SH_DENYRD`|Verweigert Lesezugriff auf die Datei|  
|`_SH_DENYNO`|Ermöglicht die Lese\- und Schreibzugriff|  
|`_SH_SECURE`|Sätze speichern Modus \(freigegebenes Lesen, einen exklusiven Schreibzugriff\).|  
  
## Siehe auch  
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)