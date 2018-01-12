---
title: _fclose_nolock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fclose_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fclose_nolock
- _fclose_nolock
dev_langs: C++
helpviewer_keywords:
- streams, closing
- fclose_nolock function
- _fclose_nolock function
ms.assetid: b4af4392-5fc8-49bb-9fe2-ca7293d3ce04
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a993376f1174a86506f5c61d3b403953bedec3f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fclosenolock"></a>_fclose_nolock
Schließt einen Stream, ohne Threads zu sperren (thread-locking).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _fclose_nolock(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger auf die `FILE`-Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `fclose` gibt 0 zurück, wenn der Stream erfolgreich geschlossen wurde. Gibt bei einem Fehler `EOF` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktionen sind eine nicht sperrende Version von `fclose`. Sie ist identisch, abgesehen davon, dass sie nicht vor Störungen durch andere Threads geschützt ist. Sie ist möglicherweise schneller, da sie nicht den Mehraufwand zum Sperren anderer Threads mit sich bringt. Verwenden Sie diese Funktion nur in threadsicheren Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen bereits der aufrufende Bereich die Threadisolation handhabt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fclose_nolock`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_schließen](../../c-runtime-library/reference/close.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)