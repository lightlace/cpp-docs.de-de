---
title: _swab | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _swab
- stdlib/_swab
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _swab
- stdlib/_swab
dev_langs: C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42515208c2c94e28ee5d6a5fab586d4ab747cc6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="swab"></a>_swab
Tauscht Bytes.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _swab(  
   char *src,  
   char *dest,  
   int n   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `src`  
 Zu kopierende und tauschende Daten.  
  
 `dest`  
 Speicherort für getauschte Daten.  
  
 `n`  
 Anzahl der zu kopierenden und tauschender Bytes.  
  
## <a name="return-value"></a>Rückgabewert
 Die Funktion `swab` gibt keinen Wert zurück. Die Funktion legt `errno` auf `EINVAL` fest, wenn entweder der `src`- oder der `dest`-Zeiger NULL oder `n` kleiner als null ist, und der Handler für ungültige Parameter wird aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).
 
## <a name="remarks"></a>Hinweise  
 Wenn `n` gerade ist, kopiert die `_swab`-Funktion `n` Bytes von `src`, tauscht jedes Paar von benachbarten Bytes und speichert das Ergebnis in `dest`. Wenn `n` ungerade ist, kopiert und tauscht `_swab` die ersten `n-1` Bytes von `src`, und das letzte Byte wird nicht kopiert. Die Funktion `_swab` wird normalerweise verwendet, um Binärdaten auf die Übertragung auf einen Computer vorzubereiten, der eine andere Bytereihenfolge verwendet.  
  
## <a name="requirements"></a>Anforderungen  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_swab`|C: \<stdlib.h> C++: \<cstdlib> oder \<stdlib.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
```C 
// crt_swab.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";  
char to[] =   "...........................";  
  
int main()  
{  
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);  
    _swab(from, to, sizeof(from));  
    printf("After:  %s\n        %s\n\n", from, to);  
}  
```  
  
```Output  
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes  
        ...........................  
  
After:  BADCFEHGJILKNMPORQTSVUXWZY  
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)