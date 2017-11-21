---
title: _fread_nolock_s2 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fread_nolock_s
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
- _fread_nolock_s
- stdio/_fread_nolock_s
dev_langs: C++
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e53f57a042216b0c910a74b4cea7c34eb1b62011
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="freadnolocks"></a>_fread_nolock_s
Liest Daten aus einem Stream, ohne andere Threads zu sperren. Diese Version von [fread_nolock](../../c-runtime-library/reference/fread-nolock.md) enthält Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t _fread_nolock_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t elementCount,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Speicherort für Daten.  
  
 `bufferSize`  
 Größe des Zielpuffers in Byte.  
  
 `elementSize`  
 Größe des zu lesenden Elements in Byte.  
  
 `elementCount`  
 Maximale Anzahl der zu lesenden Elemente.  
  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Weitere Informationen finden Sie unter [fread_s](../../c-runtime-library/reference/fread-s.md).  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion ist eine nicht sperrende Version von `fread_s`. Sie ist mit `fread_s` identisch, abgesehen davon, dass sie nicht vor Störungen durch andere Threads geschützt ist. Sie ist möglicherweise schneller, da sie nicht den Mehraufwand zum Sperren anderer Threads mit sich bringt. Verwenden Sie diese Funktion nur in threadsicheren Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen bereits der aufrufende Bereich die Threadisolation handhabt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fread_nolock_s`|C: \<stdio.h>; C++: \<cstdio> oder \<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_read](../../c-runtime-library/reference/read.md)