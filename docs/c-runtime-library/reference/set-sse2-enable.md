---
title: _set_SSE2_enable
ms.date: 04/05/2018
api_name:
- _set_SSE2_enable
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_SSE2_enable
- set_SSE2_enable
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
ms.openlocfilehash: 8838282db851c6811a3f24c75a03b31c5870e6d3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948355"
---
# <a name="_set_sse2_enable"></a>_set_SSE2_enable

Aktiviert oder deaktiviert die Verwendung von Streaming SIMD Extensions 2 (SSE2)-Anweisungen in CRT-mathematischen Routinen. (Diese Funktion ist nicht auf x64-Architekturen verfügbar, da SSE2 standardmäßig aktiviert ist.)

## <a name="syntax"></a>Syntax

```C
int _set_SSE2_enable(
   int flag
);
```

### <a name="parameters"></a>Parameter

*ssen*<br/>
1, um die SSE2-Implementierung zu aktivieren; 0, um die SSE2-Implementierung zu deaktivieren. Standardmäßig ist die SSE2-Implementierung auf Prozessoren aktiviert, die sie unterstützen.

## <a name="return-value"></a>Rückgabewert

Wert ungleich null, wenn die SSE2-Implementierung aktiviert ist; 0, wenn die SSE2-Implementierung deaktiviert ist.

## <a name="remarks"></a>Hinweise

Die folgenden Funktionen haben SSE2-Implementierungen, die mithilfe von **_set_SSE2_enable**aktiviert werden können:

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
> Wenn Sie die Compileroption [/Oi (systeminterne Funktionen generieren)](../../build/reference/oi-generate-intrinsic-functions.md) verwenden, um das Projekt zu kompilieren, kann der Eindruck entstehen, dass **_set_SSE2_enable** keine Auswirkung hat. Mit der **/Oi** -Compileroption erhält der Compiler die Berechtigung, systeminterne Funktionen zum Ersetzen von CRT-aufrufen zu verwenden. Dieses Verhalten überschreibt die Auswirkung von **_set_SSE2_enable**. Wenn Sie sicherstellen möchten, dass **/Oi** **_set_SSE2_enable**nicht außer Kraft setzt, verwenden Sie **/Oi-** , um das Projekt zu kompilieren. Dies kann auch sinnvoll sein, wenn Sie andere Compilerschalter verwenden, die **/Oi**implizieren.

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
