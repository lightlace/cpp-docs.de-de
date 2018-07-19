---
title: memcpy_s, wmemcpy_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12bf97e596a7cb4e3befa4c0633a8ef2df29a6d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403793"
---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s

Kopiert Bytes zwischen Puffern. Dabei handelt es sich um Versionen von [memcpy, wmemcpy](memcpy-wmemcpy.md) mit den unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschriebenen Erweiterungen.

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*dest*<br/>
Neuer Puffer.

*destSize*<br/>
Größe des Zielpuffers, in Bytes für memcpy_s und in Breitzeichen (wchar_t) für wmemcpy_s.

*src*<br/>
Der Puffer, aus dem kopiert werden soll.

*count*<br/>
Anzahl der zu kopierenden Zeichen.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|*dest*|*destSize*|*src*|*count*|Rückgabewert|Inhalt der *Dest*|
|------------|----------------|-----------|---|------------------|------------------------|
|alle|alle|alle|0|0|Nicht geändert|
|**NULL**|alle|alle|ungleich null|**EINVAL**|Nicht geändert|
|alle|alle|**NULL**|ungleich null|**EINVAL**|*Dest* gesetzt ist|
|alle|< *Anzahl*|alle|ungleich null|**ERANGE**|*Dest* gesetzt ist|

## <a name="remarks"></a>Hinweise

**Memcpy_s** Kopien *Anzahl* Bytes vom *Src* auf *Dest*; **Wmemcpy_s** Kopien *Anzahl* Breitzeichen (zwei Bytes). Wenn die Quelle und Ziel überlappen, ist das Verhalten des **Memcpy_s** ist nicht definiert. Verwendung **Memmove_s** um überlappende Bereiche zu behandeln.

Diese Funktionen überprüfen ihre Parameter. Wenn *Anzahl* ist ungleich NULL und *Dest* oder *Src* ist ein null-Zeiger oder *DestSize* ist kleiner als *Anzahl*, rufen diese Funktionen den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **EINVAL** oder **ERANGE** und **Errno** auf den Rückgabewert.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**memcpy_s**|\<memory.h> oder \<string.h>|
|**wmemcpy_s**|\<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
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

## <a name="see-also"></a>Siehe auch

[Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
