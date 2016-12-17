---
title: "_pclose"
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
  - "_pclose"
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
  - "_pclose"
  - "pclose"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_pclose-Funktion"
  - "pclose-Funktion"
  - "Pipes, Schließen"
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# _pclose
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wartet auf einen neuen Befehlsprozessor und schließt den Stream auf der zugeordneten Pipe.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
  
      int _pclose(  
FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Gibt den Wert vom vorherigen Aufruf von `_popen` zurück.  
  
## Rückgabewert  
 Gibt den Beendigungsstatus des beendenden Befehlsprozessors zurück oder – 1, wenn ein Fehler auftritt.  Das Format des Rückgabewerts ist nahezu mit dem von `_cwait` identisch. Der einzige Unterschied ist, dass die niederwertigen und höherwertigen Bytes vertauscht sind.  Wenn der Stream **NULL** ist, legt `_pclose``errno` auf `EINVAL` fest und gibt – 1 zurück.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_pclose`\-Funktion sucht die Prozess\-ID des Befehlsprozessors \(Cmd.exe\), der von dem zugeordneten `_popen` Aufruf gestartet wurde, führt einen [\_cwait](../../c-runtime-library/reference/cwait.md)\-Aufruf im neuen Befehlsprozessor aus und schließt den Stream auf der zugeordneten Pipe.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_pclose`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [\_pipe](../../c-runtime-library/reference/pipe.md)   
 [\_popen, \_wpopen](../../c-runtime-library/reference/popen-wpopen.md)