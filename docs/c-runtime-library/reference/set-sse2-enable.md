---
title: _set_SSE2_enable
ms.date: 04/05/2018
apiname:
- _set_SSE2_enable
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_SSE2_enable
- set_SSE2_enable
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
ms.openlocfilehash: c340423e93b6487a4a951e4b96055cba6e474269
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356536"
---
# <a name="setsse2enable"></a>_set_SSE2_enable

Aktiviert oder deaktiviert die Verwendung von Anweisungen Streaming SIMD Extensions 2 (SSE2) mathematischen CRT-Routinen. (Diese Funktion ist nicht auf x64-Architekturen verfügbar, da SSE2 standardmäßig aktiviert ist.)

## <a name="syntax"></a>Syntax

```C
int _set_SSE2_enable(
   int flag
);
```

### <a name="parameters"></a>Parameter

*flag*<br/>
1, um die SSE2-Implementierung zu aktivieren; 0, um die SSE2-Implementierung zu deaktivieren. Standardmäßig ist die SSE2-Implementierung auf Prozessoren aktiviert, die sie unterstützen.

## <a name="return-value"></a>Rückgabewert

Wert ungleich null, wenn die SSE2-Implementierung aktiviert ist; 0, wenn die SSE2-Implementierung deaktiviert ist.

## <a name="remarks"></a>Hinweise

Die folgenden Funktionen haben SSE2-Implementierung, die mithilfe von aktiviert werden, können **_set_SSE2_enable**:

- [atan](atan-atanf-atanl-atan2-atan2f-atan2l.md)

- [ceil](ceil-ceilf-ceill.md)

- [exp](exp-expf.md)

- [floor](floor-floorf-floorl.md)

- [log](log-logf-log10-log10f.md)

- [log10](log-logf-log10-log10f.md)

- [modf](modf-modff-modfl.md)

- [pow](pow-powf-powl.md)

Die SSE2-Implementierung dieser Funktionen unterscheiden sich möglicherweise geringfügig von den Standardimplementierungen, da SSE2-Zwischenwerte 64-Bit-Gleitkommamengen sind, aber die Zwischenwerte der Standardimplementierung 80-Bit-Gleitkommamengen sind.

> [!NOTE]
> Bei Verwendung der [/Oi (systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md) -Compileroption verwenden, um das Projekt zu kompilieren entsteht möglicherweise der Eindruck, die **_set_SSE2_enable** hat keine Auswirkungen. Die **/Oi** Compileroption gibt der Compiler die Berechtigung zum intrinsische Funktionen verwenden, um CRT-Aufrufe zu ersetzen; dieses Verhalten überschreibt die Auswirkung von **_set_SSE2_enable**. Sollten Sie gewährleisten, dass **/Oi** überschreibt nicht die **_set_SSE2_enable**, verwenden Sie **Oi-** das Projekt kompilieren. Dies kann auch empfehlenswert sein, wenn Sie andere compilerswitches verwenden, die die implizieren **/Oi**.

Die SSE2-Implementierung wird nur verwendet, wenn alle Ausnahmen maskiert werden. Verwenden Sie [_control87, _controlfp](control87-controlfp-control87-2.md) zum Maskieren von Ausnahmen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_set_SSE2_enable**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_set_SSE2_enable.c
// processor: x86
#include <math.h>
#include <stdio.h>

int main()
{
   int i = _set_SSE2_enable(1);

   if (i)
      printf("SSE2 enabled.\n");
   else
      printf("SSE2 not enabled; processor does not support SSE2.\n");
}
```

```Output
SSE2 enabled.
```

## <a name="see-also"></a>Siehe auch

[CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)<br/>
