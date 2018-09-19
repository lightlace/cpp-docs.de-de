---
title: memcpy, wmemcpy | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- memcpy
- wmemcpy
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
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
dev_langs:
- C++
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f75aa6a32277fda0796fe2433062f5062fdd47eb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196078"
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy

Kopiert Bytes zwischen Puffern. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [memcpy_s, wmemcpy_s](memcpy-s-wmemcpy-s.md).

## <a name="syntax"></a>Syntax

```C
void *memcpy(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemcpy(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Neuer Puffer.

*src*<br/>
Der Puffer, aus dem kopiert werden soll.

*count*<br/>
Anzahl der zu kopierenden Zeichen.

## <a name="return-value"></a>Rückgabewert

Der Wert des *Dest*.

## <a name="remarks"></a>Hinweise

**Memcpy** Kopien *Anzahl* Bytes vom *Src* zu *Dest*; **Wmemcpy** Kopien *Anzahl* Breitzeichen (zwei Bytes). Wenn sich Quelle und Ziel überlappen, ist das Verhalten der **Memcpy** ist nicht definiert. Verwendung **Memmove** um überlappende Bereiche zu behandeln.

> [!IMPORTANT]
> Stellen Sie sicher, dass der Zielpuffer dieselbe Größe wie der Quellpuffer aufweist bzw. größer ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

> [!IMPORTANT]
> Da so viele Pufferüberläufe, und daher potenzielle Sicherheitslücken, auf eine falsche Verwendung von zurückzuführen sind **Memcpy**, diese Funktion wird zwischen den "gesperrten" Funktionen von Security Development Lifecycle (SDL) aufgeführt.  Werden Sie feststellen, dass einige VC++-Bibliotheksklassen weiterhin **Memcpy**.  Darüber hinaus werden Sie feststellen, dass der VC++-compileroptimierer manchmal Aufrufe gibt **Memcpy**.  Das Visual C++-Produkt wird gemäß des SDL-Prozesses entwickelt; die Verwendung dieser gesperrten Funktion wurde daher sorgfältig geprüft.  Bei Verwendung in der Bibliothek wurden die Aufrufe sorgfältig geprüft, um sicherzustellen, dass Pufferüberläufe über diese Aufrufe nicht zulässig sind.  Im Falle des Compilers, manchmal bestimmte Codemuster werden erkannt, als identisch mit dem Muster der **Memcpy**, und werden daher mit einem Aufruf der Funktion ersetzt.  In solchen Fällen die Verwendung von **Memcpy** nicht unsicherer als die ursprünglichen Anweisungen; sie einfach wurden optimiert, die einen Aufruf der leistungsoptimierten **Memcpy** Funktion.  Genau wie die Verwendung „sicherer“ CRT-Funktionen keine Sicherheit garantiert, bedeutet die Verwendung von „gesperrten“ Funktionen keine unmittelbare Gefahr (diese müssen nur sorgfältig überprüft werden, damit die Sicherheit gewährleistet ist).
>
> Da **Memcpy** -Nutzung durch die VC++-Compiler und Bibliotheken so sorgfältig geprüft wurde, sind diese Aufrufe im Code, der ansonsten SDL kompatibel zulässig.  **Memcpy** Aufrufe, die in den Anwendungsquellcode eingeführt sind nur kompatibel mit SDL, beim Verwenden von Sicherheitsfachleuten überprüft wurde.

Die **Memcpy** und **Wmemcpy** Funktionen sind nur veraltet, wenn die Konstante **_CRT_SECURE_DEPRECATE_MEMORY** vor der inklusionsanweisung für nacheinander definiert ist die Funktionen werden als veraltet markierte, z. B. wie im folgenden Beispiel:

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

oder

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**memcpy**|\<memory.h> oder \<string.h>|
|**wmemcpy**|\<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Finden Sie unter [Memmove](memmove-wmemmove.md) ein Beispiel zur Verwendung **Memcpy**.

## <a name="see-also"></a>Siehe auch

[Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
