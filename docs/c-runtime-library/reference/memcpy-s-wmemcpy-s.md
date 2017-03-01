---
title: memcpy_s, wmemcpy_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcpy_s
- wmemcpy_s
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmemcpy_s
- memcpy_s
dev_langs:
- C++
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 38381578b8a8bd66c857d26d12a775f2af702611
ms.lasthandoff: 02/24/2017

---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s
Kopiert Bytes zwischen Puffern. Dabei handelt es sich um Versionen von [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) mit den unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschriebenen Erweiterungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t memcpy_s(  
   void *dest,  
   size_t destSize,  
   const void *src,  
   size_t count   
);  
errno_t wmemcpy_s(  
   wchar_t *dest,  
   size_t destSize,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dest`  
 Neuer Puffer.  
  
 `destSize`  
 Größe des Zielpuffers, in Bytes für memcpy_s und in Breitzeichen (wchar_t) für wmemcpy_s.  
  
 `src`  
 Der Puffer, aus dem kopiert werden soll.  
  
 `count`  
 Anzahl der zu kopierenden Zeichen.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`dest`|`destSize`|`src`|`count`|Rückgabewert|Inhalt von `dest`|  
|------------|----------------|-----------|---|------------------|------------------------|  
|any|alle|alle|0|0|Nicht geändert|  
|`NULL`|alle|alle|ungleich null|`EINVAL`|Nicht geändert|  
|alle|alle|`NULL`|ungleich null|`EINVAL`|`dest` wird auf null gesetzt|  
|alle|< `count`|alle|ungleich null|`ERANGE`|`dest` wird auf null gesetzt|  
  
## <a name="remarks"></a>Hinweise  
 `memcpy_s` kopiert `count` Bytes von `src` nach `dest`; `wmemcpy_s` kopiert `count` Breitzeichen (zwei Bytes). Wenn sich Quell und Ziel überlappen, ist das Verhalten von `memcpy_s` undefiniert. Verwendung `memmove_s` um überlappende Bereiche zu behandeln.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `count` ungleich null ist und `dest` oder `src` ein NULL-Zeiger ist, oder `destSize` kleiner als `count` ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EINVAL` oder `ERANGE` zurück und stellen den Rückgabewert auf `errno` ein.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`memcpy_s`|\<memory.h> oder \<string.h>|  
|`wmemcpy_s`|\<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_memcpy_s.c  
// Copy memory in a more secure way.  
  
#include <memory.h>  
#include <stdio.h>  
  
int main()  
{  
   int a1[10], a2[100], i;  
   errno_t err;  
  
   // Populate a2 with squares of integers  
   for (i = 0; i < 100; i++)  
   {  
      a2[i] = i*i;  
   }  
  
   // Tell memcpy_s to copy 10 ints (40 bytes), giving  
   // the size of the a1 array (also 40 bytes).  
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );      
   if (err)  
   {  
      printf("Error executing memcpy_s.\n");  
   }  
   else  
   {  
     for (i = 0; i < 10; i++)  
       printf("%d ", a1[i]);  
   }  
   printf("\n");  
}  
```  
  
```Output  
0 1 4 9 16 25 36 49 64 81   
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)
