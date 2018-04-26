---
title: memcpy, wmemcpy | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a31ada40bfab599b6da41da268bf79792f8ebf20
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

Der Wert der *Dest*.

## <a name="remarks"></a>Hinweise

**Memcpy** Kopien *Anzahl* Bytes vom *Src* auf *Dest*; **Wmemcpy** Kopien *Anzahl* Breitzeichen (zwei Bytes). Wenn die Quelle und Ziel überlappen, ist das Verhalten des **Memcpy** ist nicht definiert. Verwendung **Memmove** um überlappende Bereiche zu behandeln.

> [!IMPORTANT]
> Stellen Sie sicher, dass der Zielpuffer dieselbe Größe wie der Quellpuffer aufweist bzw. größer ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).

> [!IMPORTANT]
> Da so viele Pufferüberläufe, und daher potenzielle Sicherheitslücken, auf eine falsche Verwendung von verfolgt haben **Memcpy**, diese Funktion wird unter "gesperrten" Funktionen von Security Development Lifecycle (SDL) aufgeführt.  Möglicherweise bemerken Sie, dass einige VC++-Bibliotheksklassen weiterhin verwenden **Memcpy**.  Darüber hinaus möglicherweise beobachten Sie, dass der VC++-compileroptimierer manchmal Aufrufe ausgibt **Memcpy**.  Das Visual C++-Produkt wird gemäß des SDL-Prozesses entwickelt; die Verwendung dieser gesperrten Funktion wurde daher sorgfältig geprüft.  Bei Verwendung in der Bibliothek wurden die Aufrufe sorgfältig geprüft, um sicherzustellen, dass Pufferüberläufe über diese Aufrufe nicht zulässig sind.  Im Falle des Compilers manchmal bestimmte Codemuster werden erkannt als identisch mit dem Muster von **Memcpy**, und daher mit einem Aufruf der Funktion ersetzt.  In solchen Fällen wird die Verwendung von **Memcpy** nicht unsicherer als die ursprünglichen Anweisungen; sie sind einfach zu einem Aufruf der leistungsoptimierten optimiert **Memcpy** Funktion.  Genau wie die Verwendung „sicherer“ CRT-Funktionen keine Sicherheit garantiert, bedeutet die Verwendung von „gesperrten“ Funktionen keine unmittelbare Gefahr (diese müssen nur sorgfältig überprüft werden, damit die Sicherheit gewährleistet ist).
>
> Da **Memcpy** Auslastung durch den VC++-Compiler und Bibliotheken so sorgfältig geprüft wurde, sind diese Aufrufe innerhalb des Codes, der ansonsten SDL kompatibel ist zulässig.  **Memcpy** Aufrufe in den Anwendungsquellcode eingeführt sind nur kompatibel mit SDL, wenn diese Verwendung von Sicherheitsfachleuten überprüft wurde.

Die **Memcpy** und **Wmemcpy** Funktionen sind nur veraltet, wenn die Konstante **_CRT_SECURE_DEPRECATE_MEMORY** vor der einschlussanweisung namensweiterleitung definiert ist die Funktionen werden als veraltet markierte, z. B. wie im folgenden Beispiel:

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

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**memcpy**|\<memory.h> oder \<string.h>|
|**wmemcpy**|\<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Finden Sie unter [Memmove](memmove-wmemmove.md) ein Beispiel zum Verwenden von **Memcpy**.

## <a name="see-also"></a>Siehe auch

[Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
