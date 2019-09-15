---
title: _swab
ms.date: 11/04/2016
api_name:
- _swab
- stdlib/_swab
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _swab
- stdlib/_swab
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
ms.openlocfilehash: b0faba55c42023f4d66adae68de6be2c1ab009a0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946293"
---
# <a name="_swab"></a>_swab

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

*src*<br/>
Zu kopierende und tauschende Daten.

*dest*<br/>
Speicherort für getauschte Daten.

*n*<br/>
Anzahl der zu kopierenden und tauschender Bytes.

## <a name="return-value"></a>Rückgabewert

Die Funktion " **Swap** " gibt keinen Wert zurück. Die-Funktion legt **errno** auf **EINVAL** fest, wenn der *src* -oder *dest* -Zeiger NULL ist oder *n* kleiner als 0 (null) ist und der Handler für ungültige Parameter aufgerufen wird, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Wenn *n* gleich ist, kopiert die **_swab** -Funktion *n* Bytes aus *src*, tauscht die einzelnen Paare von angrenzenden Bytes aus und speichert das Ergebnis am *dest*. Wenn *n* ungerade ist, kopiert **_swab** die ersten *n*-1 Byte von *src*, und das endgültige Byte wird nicht kopiert. Die **_swab** -Funktion wird normalerweise verwendet, um Binärdaten für die Übertragung auf einen Computer vorzubereiten, der eine andere Byte Reihenfolge verwendet.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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
