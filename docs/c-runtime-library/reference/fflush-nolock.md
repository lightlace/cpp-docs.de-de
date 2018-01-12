---
title: _fflush_nolock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fflush_nolock
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
- fflush_nolock
- _fflush_nolock
dev_langs: C++
helpviewer_keywords:
- fflush_nolock function
- _fflush_nolock function
- streams, flushing
- flushing
ms.assetid: 5e33c4a1-b10c-4001-ad01-210757919291
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 62a4d54092e0ba2e394c9b88109a11b8b395e8e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fflushnolock"></a>_fflush_nolock
Leert einen Stream, ohne den Thread zu sperren  
  
## <a name="syntax"></a>Syntax  
  
```  
int _fflush_nolock(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger auf die `FILE`-Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Weitere Informationen finden Sie unter [fflush](../../c-runtime-library/reference/fflush.md).  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion ist eine nicht sperrende Version von `fflush`. Sie ist mit `fflush` identisch, abgesehen davon, dass sie nicht vor Störungen durch andere Threads geschützt ist. Sie ist möglicherweise schneller, da sie nicht den Mehraufwand zum Sperren anderer Threads mit sich bringt. Verwenden Sie diese Funktion nur in threadsicheren Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen bereits der aufrufende Bereich die Threadisolation handhabt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fflush_nolock`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)