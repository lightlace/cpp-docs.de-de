---
title: "_endthread, _endthreadex"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_endthread"
  - "_endthreadex"
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
  - "_endthread"
  - "endthreadex"
  - "_endthreadex"
  - "endthread"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_endthread-Funktion"
  - "endthread-Funktion"
  - "Terminieren von Threads"
  - "endthreadex-Funktion"
  - "_endthreadex-Funktion"
  - "Threading [C++], Terminieren von threads"
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# _endthread, _endthreadex
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Beendet einen Thread. `_endthread` beendet einen von `_beginthread` erstellten Thread, und  `_endthreadex` beendet einen von `_beginthreadex` erstellten Thread.  
  
## Syntax  
  
```  
void _endthread( void );  
void _endthreadex(   
   unsigned retval   
);  
```  
  
#### Parameter  
 `retval`  
 Threadexitcode.  
  
## Hinweise  
 Sie können `_endthread` oder `_endthreadex` explizit aufrufen, um einen Thread zu beenden. Allerdings wird `_endthread` oder `_endthreadex` automatisch aufgerufen, wenn der Thread aus der als Parameter an `_beginthread` oder `_beginthreadex` übergebenen Routine zurückgegeben wird. Das Beenden eines Threads durch Aufruf von `endthread` oder `_endthreadex` stellt die ordnungsgemäße Wiederherstellung der dem Thread zugeordneten Ressourcen sicher.  
  
> [!NOTE]
>  Rufen Sie für eine mit „Libcmt.lib“ verknüpfte ausführbare Datei die [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx)\-Win32\-API nicht auf, damit das Laufzeitsystem nicht an der Freigabe von zugeordneten Ressourcen gehindert wird.`_endthread` und `_endthreadex` geben zugeordnete Threadressourcen frei und rufen dann `ExitThread` auf.  
  
 `_endthread` schließt das Threadhandle automatisch. \(Dieses Verhalten unterscheidet sich von dem der `ExitThread`\-Win32\-API.\) Wenn Sie also `_beginthread` und `_endthread` verwenden, schließen Sie das Threadhandle nicht explizit mit dem Aufruf der [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx)\-Win32\-API.  
  
 Wie die `ExitThread`\-Win32\-API schließt `_endthreadex` nicht das Threadhandle. Wenn Sie also `_beginthreadex` und `_endthreadex` verwenden, müssen Sie das Threadhandle durch Aufrufen der `CloseHandle`\-Win32\-API schließen.  
  
> [!NOTE]
>  `_endthread` und `_endthreadex` führen dazu, dass im Thread ausstehende C\+\+\-Destruktoren nicht aufgerufen werden.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_endthread`|\<process.h\>|  
|`_endthreadex`|\<process.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Nur Multithread\-Versionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [\_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [\_beginthread, \_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)