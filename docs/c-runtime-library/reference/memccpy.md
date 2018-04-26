---
title: _memccpy | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _memccpy
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
- _memccpy
dev_langs:
- C++
helpviewer_keywords:
- _memccpy function
- memccpy function
ms.assetid: 9a2337df-6e85-4eba-b247-dd0532f45ddb
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 661f148e1af0877d0e961d743272de84c485ff32
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="memccpy"></a>_memccpy

Kopiert Zeichen aus einem Puffer.

## <a name="syntax"></a>Syntax

```C
void *_memccpy(
   void *dest,
   const void *src,
   int c,
   size_t count
);
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Zeiger auf das Ziel.

*src*<br/>
Zeiger auf die Quelle.

*c*<br/>
Letztes zu kopierendes Zeichen.

*count*<br/>
Anzahl der Zeichen.

## <a name="return-value"></a>Rückgabewert

Wenn das Zeichen *c* wird kopiert, **_memccpy** gibt einen Zeiger auf die "Char" im *Dest* , die unmittelbar auf das Zeichen folgt. Wenn *c* nicht kopiert wird, gibt **NULL**.

## <a name="remarks"></a>Hinweise

Die **_memccpy** 0 oder mehr Zeichen von der Funktion kopiert *Src* auf *Dest*, anhalten, wenn das Zeichen *c* kopiert wurde oder wenn *Anzahl* Zeichen kopiert wurden, welcher Fall zuerst eintritt.

**Sicherheitshinweis** Stellen Sie sicher, dass der Zielpuffer dieselbe Größe wie der Quellpuffer aufweist bzw. größer ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_memccpy**|\<memory.h> oder \<string.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_memccpy.c

#include <memory.h>
#include <stdio.h>
#include <string.h>

char string1[60] = "The quick brown dog jumps over the lazy fox";

int main( void )
{
   char buffer[61];
   char *pdest;

   printf( "Function: _memccpy 60 characters or to character 's'\n" );
   printf( "Source: %s\n", string1 );
   pdest = _memccpy( buffer, string1, 's', 60 );
   *pdest = '\0';
   printf( "Result: %s\n", buffer );
   printf( "Length: %d characters\n", strlen( buffer ) );
}
```

### <a name="output"></a>Ausgabe

```Output
Function: _memccpy 60 characters or to character 's'
Source: The quick brown dog jumps over the lazy fox
Result: The quick brown dog jumps
Length: 25 characters
```

## <a name="see-also"></a>Siehe auch

[Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
