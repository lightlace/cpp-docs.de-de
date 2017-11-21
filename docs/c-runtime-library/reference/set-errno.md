---
title: _set_errno | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_errno
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
- set_errno
- _set_errno
dev_langs: C++
helpviewer_keywords:
- errno global variable
- set_errno function
- _set_errno function
ms.assetid: d338914a-1894-4cf3-ae45-f2c4eb26590b
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2353929ea112777561697928c4f12b3e8f80a47a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="seterrno"></a>_set_errno
Legt den Wert der globalen `errno`-Variable fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _set_errno(   
   int value   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `value`  
 Der neue Wert von `errno`.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 zurück, wenn erfolgreich.  
  
## <a name="remarks"></a>Hinweise  
 Mögliche Werte sind in Errno.h definiert. Siehe auch [errno-Konstanten](../../c-runtime-library/errno-constants.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_set_errno.c  
#include <stdio.h>  
#include <errno.h>  
  
int main()  
{  
   _set_errno( EILSEQ );  
   perror( "Oops" );  
}  
```  
  
```Output  
Oops: Illegal byte sequence  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_set_errno`|\<stdlib.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [_get_errno](../../c-runtime-library/reference/get-errno.md)   
 [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)