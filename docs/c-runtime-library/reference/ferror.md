---
title: ferror | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ferror
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
- ferror
dev_langs:
- C++
helpviewer_keywords:
- ferror function
- streams, testing for errors
- errors [C++], testing for stream
ms.assetid: 528a34bc-f2aa-4c3f-b89a-5b148e6864f7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 1828b9316cf29d953a6db8f8a6c11b5a3a08c346
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="ferror"></a>ferror
Testet auf einen Fehler in einem Stream  
  
## <a name="syntax"></a>Syntax  
  
```  
int ferror(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn kein in `stream` Fehler aufgetreten ist, gibt `ferror` 0 zurück. Andernfalls gibt es einen Wert ungleich 0 (null) zurück. Wenn der Stream `NULL` ist, ruft `ferror` den ungültigen Parameterhandler wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben auf. Wenn die weitere Ausführung zugelassen wird, setzt diese Funktion `errno` auf `EINVAL` und gibt "0" zurück.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `ferror`-Routine, die sowohl als Funktion als auch als Makro implementiert wird, testet auf einen Lese- oder Schreibfehler in der `stream` zugeordneten Datei. Wenn ein Fehler aufgetreten ist, bleibt der Fehlerindikator für den Stream festgelegt, bis der Stream geschlossen oder zurückgespult wird oder bis `clearerr` dagegen aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`ferror`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Sehen Sie sich das Beispiel für [feof](../../c-runtime-library/reference/feof.md) an.  
  
## <a name="see-also"></a>Siehe auch  
 [Error Handling (Fehlerbehandlung)](../../c-runtime-library/error-handling-crt.md)   
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)
