---
title: _get_errno | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_errno
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
f1_keywords: _get_errno
dev_langs: C++
helpviewer_keywords:
- get_errno function
- errno global variable
- _get_errno function
ms.assetid: b3fd5ebc-f41b-4314-a2f4-2f2d79d6e740
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 53adc2ce18b5442320511391f4848682520e3a26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="geterrno"></a>_get_errno
Ruft den aktuellen Wert der globalen errno-Variable ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _get_errno(   
   int * pValue   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pValue`  
 Ein Zeiger auf eine ganze Zahl, die durch den aktuellen Wert der `errno`-Variable ersetzt werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null) zurück, wenn der Vorgang erfolgreich war. Wenn ein Fehler auftritt, erscheint ein Fehlercode. Wenn `pValue` `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EINVAL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Mögliche Werte von `errno` sind in Errno.h definiert. Siehe auch [errno-Konstanten](../../c-runtime-library/errno-constants.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_get_errno.c  
#include <stdio.h>  
#include <fcntl.h>  
#include <sys/stat.h>  
#include <share.h>  
#include <errno.h>  
  
int main()  
{  
   errno_t err;  
   int pfh;  
   _sopen_s( &pfh, "nonexistent.file", _O_WRONLY, _SH_DENYNO, _S_IWRITE );  
   _get_errno( &err );  
   printf( "errno = %d\n", err );  
   printf( "fyi, ENOENT = %d\n", ENOENT );  
}  
```  
  
```Output  
errno = 2  
fyi, ENOENT = 2  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_get_errno`|\<stdlib.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [_set_errno](../../c-runtime-library/reference/set-errno.md)   
 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)