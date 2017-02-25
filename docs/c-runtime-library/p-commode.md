---
title: "__p__commode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__p__commode"
apilocation: 
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__p__commode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__p__commode"
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# __p__commode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zeigt auf die globale Variable `_commode`, die dem Standarddateicommitmodus für Datei\-E\/A\-Vorgänge angibt.  
  
## Syntax  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## Rückgabewert  
 Zeiger der globalen Variable `_commode`.  
  
## Hinweise  
 Die Funktion `__p__commode` ist nur für die interne Verwendung gedacht und sollte nicht vom Benutzercode aufgerufen werden.  
  
 Dateicommitmodus gibt an, wenn wichtige Daten auf den Datenträger geschrieben werden.  Weitere Informationen finden Sie unter [fflush](../c-runtime-library/reference/fflush.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_p\_\_commode|internal.h|