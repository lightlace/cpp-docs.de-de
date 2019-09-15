---
title: memcpy, wmemcpy
ms.date: 11/04/2016
api_name:
- memcpy
- wmemcpy
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: e9d947dc4e9ecea654e8cb16e957887fe4360161
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951852"
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

Der Wert von *dest*.

## <a name="remarks"></a>Hinweise

**memcpy** kopiert *Anzahl* Bytes von *src* auf *dest*. **wmemcpy** kopiert die *Anzahl* von breit Zeichen (zwei Bytes). Wenn sich Quelle und Ziel überlappen, ist das Verhalten von **memcpy** nicht definiert. Verwenden Sie **memmove** zum Verarbeiten überlappenden Bereiche.

> [!IMPORTANT]
> Stellen Sie sicher, dass der Zielpuffer dieselbe Größe wie der Quellpuffer aufweist bzw. größer ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/win32/SecBP/avoiding-buffer-overruns).

> [!IMPORTANT]
> Da so viele Pufferüberläufe und somit potenzielle Sicherheits Exploits auf eine nicht ordnungsgemäße Verwendung von **memcpy**zurückzuführen sind, wird diese Funktion unter den "gesperrten" Funktionen durch den Security Development Lifecycle (SDL) aufgelistet.  Möglicherweise stellen Sie fest, dass einige VC + +-Bibliotheks Klassen **memcpy**weiterhin verwenden.  Darüber hinaus können Sie feststellen, dass der VC + +-compileroptimierer manchmal Aufrufe an **memcpy**ausgibt.  Das Visual C++-Produkt wird gemäß des SDL-Prozesses entwickelt; die Verwendung dieser gesperrten Funktion wurde daher sorgfältig geprüft.  Bei Verwendung in der Bibliothek wurden die Aufrufe sorgfältig geprüft, um sicherzustellen, dass Pufferüberläufe über diese Aufrufe nicht zulässig sind.  Im Falle des Compilers werden manchmal bestimmte Code muster als identisch mit dem Muster von **memcpy**erkannt und daher durch einen-Aufrufausdruck ersetzt.  In solchen Fällen ist die Verwendung von **memcpy** nicht unsicherer als die ursprünglichen Anweisungen. Sie wurden einfach für einen aufrufungoptimierter **memcpy** -Funktion optimiert.  Genau wie die Verwendung „sicherer“ CRT-Funktionen keine Sicherheit garantiert, bedeutet die Verwendung von „gesperrten“ Funktionen keine unmittelbare Gefahr (diese müssen nur sorgfältig überprüft werden, damit die Sicherheit gewährleistet ist).
>
> Da die **memcpy** -Verwendung durch den VC + +-Compiler und Bibliotheken so sorgfältig geprüft wurde, sind diese Aufrufe in Code zulässig, der andernfalls SDL kompatibel ist.  **memcpy** -Aufrufe, die im Quellcode der Anwendung eingeführt wurden, sind nur kompatibel mit SDL, wenn diese Verwendung von Sicherheitsexperten geprüft wurde.

Die **memcpy** -Funktion und die **wmemcpy** -Funktion sind nur veraltet, wenn die Konstante **_CRT_SECURE_DEPRECATE_MEMORY** vor der Einschluss Anweisung definiert wird, damit die Funktionen als veraltet markiert werden, z. b. im folgenden Beispiel:

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

Ein Beispiel für die Verwendung von **memcpy**finden Sie unter [memmove](memmove-wmemmove.md) .

## <a name="see-also"></a>Siehe auch

[Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
