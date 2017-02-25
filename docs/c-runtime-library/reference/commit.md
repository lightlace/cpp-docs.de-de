---
title: "_commit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_commit"
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
  - "_commit"
  - "commit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_commit-Funktion"
  - "commit-Funktion"
  - "Übernehmen von Dateien auf einen Datenträger"
  - "Dateien [C++], Leeren"
  - "Leeren von Dateien auf einem Datenträger"
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _commit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Leert eine Datei direkt dem Datenträger.  
  
## Syntax  
  
```  
int _commit(   
   int fd   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor, der die geöffnete Datei verweist.  
  
## Rückgabewert  
 `_commit` gibt 0 zurück, wenn die Datei erfolgreich auf dem Datenträger geschrieben wurde.  Bei dem Rückgabewert von 1 gibt einen Fehler an.  
  
## Hinweise  
 Die Funktion `_commit` wird das Betriebssystem, um die Datei zu schreiben, die mit `fd` auf einem Datenträger zugeordnet ist.  Dieser Aufruf stellt sicher, dass die angegebene Datei sofort geleert wird, nicht für die Inline\-Erweiterung des Betriebssystems.  
  
 Wenn `fd` ein ungültiger Dateideskriptor ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, gibt die Funktion \-1 zurück und `errno` ist auf `EBADF` festgelegt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`_commit`|\<io.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [E\/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_read](../../c-runtime-library/reference/read.md)   
 [\_write](../../c-runtime-library/reference/write.md)