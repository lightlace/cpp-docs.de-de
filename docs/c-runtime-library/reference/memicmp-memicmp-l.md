---
title: _memicmp, _memicmp_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _memicmp_l
- _memicmp
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
- _memicmp
- memicmp_l
- _memicmp_l
dev_langs:
- C++
helpviewer_keywords:
- memicmp function
- _memicmp function
- memicmp_l function
- _memicmp_l function
ms.assetid: 0a6eb945-4077-4f84-935d-1aaebe8db8cb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25540061a3c7b405dcd173c6aa3d28678551c78d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="memicmp-memicmpl"></a>_memicmp, _memicmp_l

Vergleicht Zeichen in zwei Puffern (ohne Berücksichtigung der Groß- und Kleinschreibung).

## <a name="syntax"></a>Syntax

```C
int _memicmp(
   const void *buffer1,
   const void *buffer2,
   size_t count
);
int _memicmp_l(
   const void *buffer1,
   const void *buffer2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*buffer1*<br/>
Erster Puffer.

*buffer2*<br/>
Zweite Puffer.

*count*<br/>
Anzahl der Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert gibt die Beziehung zwischen den Puffern an.

|Rückgabewert|Beziehung der ersten count-Zeichen von buf1 und buf2|
|------------------|--------------------------------------------------------|
|< 0|*buffer1* kleiner als *buffer2*.|
|0|*buffer1* identisch mit *buffer2*.|
|> 0|*buffer1* größer als *buffer2*.|
|**_NLSCMPERROR**|Es ist ein Fehler aufgetreten.|

## <a name="remarks"></a>Hinweise

Die **_memicmp** Funktion vergleicht die ersten *Anzahl* Zeichen der zwei Puffer *buffer1* und *buffer2* byteweise. Beim Vergleich wird die Groß-/Kleinschreibung nicht berücksichtigt.

Wenn entweder *buffer1* oder *buffer2* ist ein null-Zeiger, ruft diese Funktion einen Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion **_NLSCMPERROR** und legt **Errno** auf **EINVAL**.

**_memicmp** verwendet das aktuelle Gebietsschema für gebietsschemaabhängige Verhalten. **_memicmp_l** ist nahezu identisch, das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_memicmp**|\<memory.h> oder \<string.h>|
|**_memicmp_l**|\<memory.h> oder \<string.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_memicmp.c
// This program uses _memicmp to compare
// the first 29 letters of the strings named first and
// second without regard to the case of the letters.

#include <memory.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   int result;
   char first[] = "Those Who Will Not Learn from History";
   char second[] = "THOSE WHO WILL NOT LEARN FROM their mistakes";
   // Note that the 29th character is right here ^

   printf( "Compare '%.29s' to '%.29s'\n", first, second );
   result = _memicmp( first, second, 29 );
   if( result < 0 )
      printf( "First is less than second.\n" );
   else if( result == 0 )
      printf( "First is equal to second.\n" );
   else if( result > 0 )
      printf( "First is greater than second.\n" );
}
```

```Output
Compare 'Those Who Will Not Learn from' to 'THOSE WHO WILL NOT LEARN FROM'
First is equal to second.
```

## <a name="see-also"></a>Siehe auch

[Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
