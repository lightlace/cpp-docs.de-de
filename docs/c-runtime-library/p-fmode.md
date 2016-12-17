---
title: "__p__fmode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "__p__fmode"
apilocation: 
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__p__fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__p__fmode"
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# __p__fmode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zeigt auf die globale Variable `_fmode`, die dem Standarddateiübersetzungsmodus für Datei\-E\/A\-Vorgänge angibt.  
  
## Syntax  
  
```cpp  
int* __p__fmode(  
   );  
```  
  
## Rückgabewert  
 Zeiger der globalen Variable `_fmode`.  
  
## Hinweise  
 Die Funktion `__p__fmode` ist nur für die interne Verwendung gedacht und sollte nicht vom Benutzercode aufgerufen werden.  
  
 Dateiübersetzungsmodus gibt entweder `binary` oder `text` Übersetzung für [\_open](../c-runtime-library/reference/open-wopen.md) und [\_pipe](../c-runtime-library/reference/pipe.md) E\/A\-Vorgänge an.  Weitere Informationen finden Sie unter [\_fmode](../c-runtime-library/fmode.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_p\_\_fmode|stdlib.h|