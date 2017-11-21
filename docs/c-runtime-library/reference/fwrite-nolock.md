---
title: _fwrite_nolock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fwrite_nolock
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
- _fwrite_nolock
- fwrite_nolock
dev_langs: C++
helpviewer_keywords:
- fwrite_nolock function
- streams, writing data to
- _fwrite_nolock function
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a40c6c2c4639697b75424c38250143312d53cdc0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="fwritenolock"></a>_fwrite_nolock
Schreibt ein Zeichen in einen Stream, ohne den Thread zu sperren.  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t _fwrite_nolock(  
   const void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Zeiger auf die zu schreibenden Daten.  
  
 `size`  
 Elementgröße in Bytes.  
  
 `count`  
 Maximale Anzahl zu schreibender Elemente.  
  
 `stream`  
 Zeiger auf die `FILE`-Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Identisch mit [fwrite](../../c-runtime-library/reference/fwrite.md).  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion ist eine nicht sperrende Version von `fwrite`. Sie ist mit `fwrite` identisch, abgesehen davon, dass sie nicht vor Störungen durch andere Threads geschützt ist. Sie ist möglicherweise schneller, da sie nicht den Mehraufwand zum Sperren anderer Threads mit sich bringt. Verwenden Sie diese Funktion nur in threadsicheren Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen bereits der aufrufende Bereich die Threadisolation handhabt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fwrite_nolock`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [fread](../../c-runtime-library/reference/fread.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_write](../../c-runtime-library/reference/write.md)