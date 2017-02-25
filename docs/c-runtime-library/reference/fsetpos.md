---
title: "fsetpos | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fsetpos"
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
  - "fsetpos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fsetpos-Funktion"
  - "Streams, Festlegen von Positionsindikatoren"
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# fsetpos
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt den Stellungsanzeiger fest.  
  
## Syntax  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
 `pos`  
 Position\-Indikatorspeicher.  
  
## Rückgabewert  
 Wenn erfolgreich, `fsetpos` gibt 0 zurück.  Auf Fehler gibt die Funktion einen Wert ungleich 0 \(null\) zurück und legt `errno` auf eine der folgenden Manifestkonstanten fest \(in ERRNO.H\): `EBADF`, die die Datei bedeutet, ist jedoch nicht zugänglich oder das Objekt, in denen `stream` auf keine gültige Dateistruktur ist; oder `EINVAL`, die einen ungültigen Wert für `stream` oder `pos` bedeutet, wurde übergeben.  Wenn ein ungültiger Parameter übergeben wird, rufen diese Funktionen den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Funktion `fsetpos` wird der Stellungsanzeiger für `stream` auf den Wert `pos`*fest,* der in einem früheren Aufruf von `fgetpos` für `stream` aufgerufen wird *.* Die Funktion löscht den Dateiende\-Indikator und macht alle Effekte von [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) auf `stream`*rückgängig.* Nachdem die `fsetpos` aufgerufen hat, wird der folgende Operation möglicherweise auf `stream` entweder oder Ausgabe eingegeben.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fsetpos`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [fgetpos](../../c-runtime-library/reference/fgetpos.md).  
  
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)