---
title: "_setmaxstdio"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_setmaxstdio"
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
  - "setmaxstdio"
  - "_setmaxstdio"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmaxstdio-Funktion"
  - "Maximale offene Dateien"
  - "Offene Dateien, Maximum"
  - "setmaxstdio-Funktion"
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _setmaxstdio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt ein Maximum für die Anzahl von gleichzeitig geöffneten Dateien mit den verschiedenen `stdio` fest.  
  
## Syntax  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### Parameter  
 `newmax`  
 Neues Maximum für die Anzahl von gleichzeitig geöffneten Dateien bei `stdio` auf Prozessebene.  
  
## Rückgabewert  
 Gibt `newmax` zurück, wenn dies; \- 1 andernfalls.  
  
 Wenn `newmax` kleiner als `_IOB_ENTRIES` oder dann die maximale Anzahl von Handles größer ist, die im Betriebssystem vorhanden sind, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, legt gibt diese Funktion \-1 und `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_setmaxstdio`\-Funktion änder der maximale Wert für die Anzahl der Dateien, die möglicherweise gleichzeitig bei den verschiedenen `stdio` geöffnet sind.  
  
 C\-Laufzeit E\/A unterstützt jetzt viele weitere Dateien geöffnet auf Win32\-Plattformen als in früheren Versionen.  Bis 2.048 Dateien können unter [lowio Seitenebene](../../c-runtime-library/low-level-i-o.md) geöffnet sein \(das heißt, geöffnet und mittels `_open`, `_read`, `_write`, z. B. Familie von E\/A\-Funktionen zugegriffen\).  Bis 512 Dateien können unter [stdio Seitenebene](../../c-runtime-library/stream-i-o.md) geöffnet sein \(das heißt, geöffnet und mittels `fopen`, `fgetc`, `fputc`, z. B. Familie von Funktionen zugegriffen\).  Die Beschränkung von 512 geöffneten Dateien auf der `stdio` Ebene kann auf maximal 2.048 mithilfe der Funktion `_setmaxstdio` erhöht werden.  
  
 Da e\-stufig Funktionen wie `stdio`, `fopen`, auf die `lowio`\-Funktionen erstellt werden, ist das Maximum von 2.048 eine aufwändige Obergrenze für die Anzahl der gleichzeitig geöffneten Dateien, die von der C\-Laufzeitbibliothek zugegriffen werden.  
  
> [!NOTE]
>  Diese Obergrenze kann über das hinausgeht, was durch eine bestimmte Win32\-Plattform und \- konfiguration unterstützt wird.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_setmaxstdio`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Unter [\_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md) finden Sie ein Beispiel für die Verwendung von `_setmaxstdio`.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)