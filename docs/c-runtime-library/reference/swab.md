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
ms.openlocfilehash: 2975e63f79818e5eac430056258b72b9c6641a49
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100273"
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

*src*<br/>
Zu kopierende und tauschende Daten.

*dest*<br/>
Speicherort für getauschte Daten.

*n*<br/>
Anzahl der zu kopierenden und tauschender Bytes.

## <a name="return-value"></a>Rückgabewert

Die **Swab** Funktion gibt keinen Wert zurück. Legt die Funktion **Errno** zu **EINVAL** Wenn entweder die *Src* oder *Dest* Zeiger null ist oder *n* liegt als 0 (null), und der ungültige Parameter Handler wird aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Wenn *n* gerade ist, die **_swab** -Funktion kopiert *n* Bytes vom *Src*, tauscht jedes Paar von benachbarten Bytes und speichert das Ergebnis in *Dest*. Wenn *n* ungerade ist, **_swab** kopiert und tauscht die erste *n*-1 Byte der *Src*, und das letzte Byte wird nicht kopiert. Die **_swab** Funktion wird in der Regel verwendet, um binäre Daten für die Übertragung auf einen Computer vorzubereiten, die eine andere Bytereihenfolge verwendet.

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
