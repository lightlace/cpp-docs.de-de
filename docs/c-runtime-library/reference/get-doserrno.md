---
title: "_get_doserrno | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_doserrno"
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
  - "_get_doserrno"
  - "get_doserrno"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_doserrno-Funktion"
  - "get_doserrno-Funktion"
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _get_doserrno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den vom Betriebssystem zurückgegebenen Fehlerwert ab, bevor dieser in einen `errno`\-Wert übersetzt wird.  
  
## Syntax  
  
```  
errno_t _get_doserrno(     int * pValue  );   
```  
  
#### Parameter  
 \[out\] `pValue`  
 Ein Zeiger auf eine Ganzzahl, die durch den aktuellen Wert des globalen Makros `_doserrno` ersetzt werden soll.  
  
## Rückgabewert  
 Wenn `_get_doserrno` erfolgreich verläuft, gibt es 0 zurück, andernfalls einen Fehlercode.  Wenn `pValue` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
## Hinweise  
 Das globale Makro `_doserrno` wird bei der CRT\-Initialisierung auf Null gesetzt, bevor die Prozessausführung beginnt.  Es wird auf einen Betriebssystemfehlerwert gesetzt, der von jeder Funktion auf Systemebene zurückgegeben wird, die einen Betriebssystemfehler zurückgibt, und wird während der Ausführung niemals auf Null gesetzt.  Wenn Sie Code schreiben, um den von einer Funktion zurückgegebenen Fehlerwert zu prüfen, löschen Sie vor dem Funktionsaufruf immer `_doserrno` durch Anwendung von [\_set\_doserrno](../../c-runtime-library/reference/set-doserrno.md).  Da eine andere Funktion `_doserrno` überschreiben könnte, prüfen Sie unmittelbar nach dem Funktionsaufruf den Wert durch Anwendung von `_get_doserrno`.  
  
 Für übertragbare Fehlercodes wird [\_get\_errno](../../c-runtime-library/reference/get-errno.md) statt `_get_doserrno` empfohlen.  
  
 Mögliche Werte von `_doserrno` sind in \<errno.h\> definiert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_get_doserrno`|\<stdlib.h\>, \<cstdlib\> \(C\+\+\)|\<errno.h\>, \<cerrno\> \(C\+\+\)|  
  
 `_get_doserrno` ist eine Microsoft\-Erweiterung.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [\_set\_doserrno](../../c-runtime-library/reference/set-doserrno.md)   
 [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)