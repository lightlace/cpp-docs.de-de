---
title: _swab | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeedb217466262d8643a851b5f93cb9ac26fb0a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="swab"></a>_swab

Tauscht Bytes.

## <a name="syntax"></a>Syntax

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>Parameter

*Src* Daten kopiert und ausgetauscht werden.

*Dest* Speicherort für Daten ausgetauscht.

*n* Anzahl von Bytes, die kopiert und ausgetauscht werden.

## <a name="return-value"></a>Rückgabewert

Die **Swab** -Funktion gibt keinen Wert zurück. Die Funktion legt **Errno** auf **EINVAL** Wenn entweder die *Src* oder *Dest* Zeiger null ist oder *n* kleiner als 0 (null), und mit dem ungültigen Parameter Handler aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Wenn *n* geraden Wert hat, ist die **_swap** -Funktion kopiert *n* Bytes vom *Src*jedes Paar von benachbarten Bytes vertauscht und speichert das Ergebnis an *Dest*. Wenn *n* ungerade ist, **_swap** kopiert und die erste vertauscht *n*-1 Byte der *Src*, und das letzte Byte wird nicht kopiert. Die **_swap** Funktion ist in der Regel verwendet, um binäre Daten für die Übertragung an einen Computer vorzubereiten, die einen anderen Bytereihenfolge verwendet.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> oder \<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

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

[Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)<br/>
