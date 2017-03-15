---
title: "_set_doserrno | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_doserrno"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_doserrno"
  - "set_doserrno"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_doserrno (globale Variable)"
  - "_set_doserrno-Funktion"
  - "doserrno (globale Variable)"
  - "set_doserrno-Funktion"
ms.assetid: 8686c159-3797-4705-a53e-7457869ca6f3
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _set_doserrno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt den Wert der globalen Variablen [\_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) fest.  
  
## Syntax  
  
```  
errno_t _set_doserrno(   
   int value   
);  
```  
  
#### Parameter  
 \[in\] `value`  
 Der neue Wert von `_doserrno`.  
  
## Rückgabewert  
 Gibt null zurück, wenn der Vorgang erfolgreich ist.  
  
## Hinweise  
 Mögliche Werte werden in Errno.h definiert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_set_doserrno`|\<stdlib.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [\_get\_doserrno](../../c-runtime-library/reference/get-doserrno.md)   
 [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)