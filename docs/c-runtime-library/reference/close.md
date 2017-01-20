---
title: "_close"
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
  - "_close"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_close"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_close-Funktion"
  - "close-Funktion"
  - "Dateien [C++], Schließen"
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schließt eine Datei.  
  
## Syntax  
  
```  
int _close(   
   int fd   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor, der die geöffnete Datei verweist.  
  
## Rückgabewert  
 `_close` gibt 0 zurück, wenn die Datei erfolgreich geschlossen wurde.  Bei dem Rückgabewert von 1 gibt einen Fehler an.  
  
## Hinweise  
 Die `_close`\-Funktion enthält die Datei, die `fd` zugeordnet ist.  
  
 Der Dateideskriptor und das zugrunde liegende Betriebssystemdateihandle werden geschlossen.  Daher ist es nicht erforderlich, `CloseHandle` aufzurufen, wenn die Datei ursprünglich mit der Win32\-Funktion `CreateFile` geöffnet war und einem Dateideskriptor mit `_open_osfhandle` konvertiert.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `fd` ein ungültiger Dateideskriptor ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, gibt Funktionen \-1 zurück und `errno` ist auf `EBADF` festgelegt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_close`|\<io.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [\_open](../../c-runtime-library/reference/open-wopen.md).  
  
## Siehe auch  
 [E\/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_unlink, \_wunlink](../../c-runtime-library/reference/unlink-wunlink.md)