---
title: "_chsize_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chsize_s"
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
  - "chsize_s"
  - "_chsize_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chsize_s-Funktion"
  - "chsize_s-Funktion"
  - "Dateien [C++], Ändern der Größe"
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _chsize_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe einer Datei.  Dies ist eine Version von [\_chsize](../../c-runtime-library/reference/chsize.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor, der eine geöffnete Datei verweist.  
  
 `size`  
 Neue Länge einer Datei in Bytes.  
  
## Rückgabewert  
 `_chsize_s`  gibt den Wert 0 zurück, wenn die Dateigröße erfolgreich geändert wird.  Bei dem Rückgabewert ungleich 0 \(null\) gibt einen Fehler an: der Rückgabewert ist `EACCES` , wenn die angegebene Datei mit Zugriff beschränkt ist, `EBADF` , wenn die angegebene Datei schreibgeschützt ist, der ein oder ungültig ist, `ENOSPC` , wenn kein Platz auf dem Gerät vorhanden ist, oder `EINVAL` , wenn Größe kleiner als null ist.  `errno`  wird auf den Wert festgelegt.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_chsize_s` \-Funktion erweitert oder schneidet die Datei ab, die mit `fd` zur Länge zugeordnet wird, die von `size` angegeben wird.  Die Datei muss in einem Modus geöffnet werden, ermöglicht der zu schreiben.  NULL\-Zeichen \("\\ 0 "\) angefügt werden, wenn sie erweitert wird.  Wenn die Datei abgeschnitten wird, wurden alle Daten vom Ende der komprimierten Datei zur ursprünglichen Größe der Datei verloren.  
  
 `_chsize_s`  nimmt eine 64\-Bit\-Ganzzahl als die Dateigröße und Dateigrößen kann größer als 4 GB daher behandeln.  Ein `_chsize`  wird an 32\-Bit\-Dateigrößen beschränkt.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `fd` kein gültiger Dateideskriptor ist, Größe oder kleiner als null ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_chsize_s`|\<io.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)