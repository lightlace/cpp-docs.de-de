---
title: _endthread, _endthreadex | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _endthread
- _endthreadex
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 794dc5c4bbaf9653c5b6bbb08ea3e0a60ca438c4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex
Beendet einen Thread. `_endthread` beendet einen von `_beginthread` erstellten Thread, und  `_endthreadex` beendet einen von `_beginthreadex`erstellten Thread.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _endthread( void );  
void _endthreadex(   
   unsigned retval   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `retval`  
 Threadexitcode.  
  
## <a name="remarks"></a>Hinweise  
 Sie können `_endthread` oder `_endthreadex` explizit aufrufen, um einen Thread zu beenden. Allerdings wird `_endthread` oder `_endthreadex` automatisch aufgerufen, wenn der Thread aus der als Parameter an `_beginthread` oder `_beginthreadex`übergebenen Routine zurückgegeben wird. Das Beenden eines Threads durch Aufruf von `endthread` oder `_endthreadex` stellt die ordnungsgemäße Wiederherstellung der dem Thread zugeordneten Ressourcen sicher.  
  
> [!NOTE]
>  Rufen Sie für eine mit „Libcmt.lib“ verknüpfte ausführbare Datei die [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) -Win32-API nicht auf, damit das Laufzeitsystem nicht an der Freigabe von zugeordneten Ressourcen gehindert wird. `_endthread` und `_endthreadex` geben zugeordnete Threadressourcen frei und rufen dann `ExitThread`auf.  
  
 `_endthread` schließt das Threadhandle automatisch. (Dieses Verhalten unterscheidet sich von dem der `ExitThread`-Win32-API.) Wenn Sie also `_beginthread` und `_endthread` verwenden, schließen Sie das Threadhandle nicht explizit mit dem Aufruf der [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx)-Win32-API.  
  
 Wie die `ExitThread` -Win32-API schließt `_endthreadex` nicht das Threadhandle. Wenn Sie also `_beginthreadex` und `_endthreadex` verwenden, müssen Sie das Threadhandle durch Aufrufen der `CloseHandle`-Win32-API schließen.  
  
> [!NOTE]
>  `_endthread` und `_endthreadex` führen dazu, dass im Thread ausstehende C++-Destruktoren nicht aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_endthread`|\<process.h>|  
|`_endthreadex`|\<process.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Multithread-Versionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Weitere Informationen finden Sie im Beispiel für [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)