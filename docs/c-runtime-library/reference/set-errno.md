---
title: "_set_errno | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_errno"
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
  - "set_errno"
  - "_set_errno"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_errno-Funktion"
  - "errno (globale Variable)"
  - "set_errno-Funktion"
ms.assetid: d338914a-1894-4cf3-ae45-f2c4eb26590b
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _set_errno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legen Sie den Wert der globalen Variablen `errno` fest.  
  
## Syntax  
  
```  
errno_t _set_errno(   
   int value   
);  
```  
  
#### Parameter  
 \[in\] `value`  
 Der neue Wert von `errno`.  
  
## Rückgabewert  
 Gibt null zurück, wenn der Vorgang erfolgreich ist.  
  
## Hinweise  
 Mögliche Werte werden in Errno.h definiert.  Siehe auch [errno\-Konstanten](../../c-runtime-library/errno-constants.md).  
  
## Beispiel  
  
```  
// crt_set_errno.c  
#include <stdio.h>  
#include <errno.h>  
  
int main()  
{  
   _set_errno( EILSEQ );  
   perror( "Oops" );  
}  
```  
  
  **Oops: Ungültige Bytesequenz**   
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_set_errno`|\<stdlib.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [\_get\_errno](../../c-runtime-library/reference/get-errno.md)   
 [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)