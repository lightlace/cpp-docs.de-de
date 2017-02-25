---
title: "_get_fmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_fmode"
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
  - "get_fmode"
  - "_get_fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_fmode-Funktion"
  - "Dateiübersetzung [C++], Standardmodus"
  - "get_fmode-Funktion"
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _get_fmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Standarddateiübersetzungsmodus für Datei\-E\/A\-Vorgänge ab.  
  
## Syntax  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### Parameter  
 \[out\] `pmode`  
 Ein Zeiger auf eine mit der aktuellen Standardmodus zu füllenden Integer: `_O_TEXT` oder `_O_BINARY`.  
  
## Rückgabewert  
 Gibt null zurück, wenn dies; ein Fehlercode auf Fehler.  Wenn `pmode``NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `EINVAL` zurück.  
  
## Hinweise  
 Die Funktion ruft den Wert der globalen Variablen [\_fmode](../../c-runtime-library/fmode.md) ab.  Diese Variable gibt den Standarddateiübersetzungsmodus für und Streamdatei\-e\/a\-Vorgänge die systemnahen, wie `_open`, `_pipe`, `fopen` und `freopen` an.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_get_fmode`|\<stdlib.h\>|\<fcntl.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Siehe das Beispiel in [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md).  
  
## Entsprechung in .NET Framework  
 Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [\_fmode](../../c-runtime-library/fmode.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [Text\- und Binärmodusdatei\-E\/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md)