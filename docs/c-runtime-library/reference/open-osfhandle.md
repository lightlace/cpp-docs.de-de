---
title: "_open_osfhandle"
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
  - "_open_osfhandle"
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
  - "_open_osfhandle"
  - "open_osfhandle"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "open_osfhandle-Funktion"
  - "Dateihandles [C++], Zuordnen"
  - "_open_osfhandle-Funktion"
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# _open_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ordnet Wechselstromablaufdateideskriptor mit einem vorhandenen Dateihandle des Betriebssystems zu.  
  
## Syntax  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### Parameter  
 `osfhandle`  
 Dateihandle des Betriebssystems.  
  
 `flags`  
 Typen aus den Vorgängen können.  
  
## Rückgabewert  
 Wenn erfolgreich, gibt `_open_osfhandle` Wechselstrom\-Laufzeitdateideskriptor zurück.  Andernfalls wird \- 1 zurück.  
  
## Hinweise  
 Die `_open_osfhandle`\-Funktion wird Wechselstromablaufdateideskriptor zu und ordnet ihn dem Dateihandle des Betriebssystems zu, das von `osfhandle` angegeben wird.  Das `flags`\-Argument ist ein ganzzahliger Ausdruck, der aus einer oder mehreren der Manifestkonstanten besteht, die in Fcntl.h definiert werden.  Wenn zwei oder mehr Konstanten Manifest verwendet werden, um das Argument `flags` zu bilden, werden die Konstanten der bitweisen Operator OR kombiniert \(  **&#124;** \).  
  
 definiert die folgenden Fcntl.h Manifestkonstanten.  
  
 **\_O\_APPEND**  
 Positioniert einen Dateizeiger am Ende der Datei vor jedem Schreibvorgänge.  
  
 **\_O\_RDONLY**  
 Öffnet die Datei nur für Lesezwecke.  
  
 **\_O\_TEXT**  
 Öffnet die Datei im Modus des Texts \(übersetzt\).  
  
 **\_O\_WTEXT**  
 Öffnet die Datei im Modus des übersetztes Unicode \(UTF\-16\).  
  
 Um eine Datei zu schließen, die mit `_open_osfhandle` geöffnet ist, rufen Sie `_close` auf.  Das zugrunde liegende Handle wird auch durch den Aufruf `_close` geschlossen, ist daher nicht erforderlich, die Win32\-Funktion `CloseHandle` im anfänglichen Handle aufzurufen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_open_osfhandle`|\<io.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)