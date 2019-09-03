---
title: intrinsic-Pragma
ms.date: 08/29/2019
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
ms.openlocfilehash: bb4403abf5e278ed3727af660579e22ab69592c7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220941"
---
# <a name="intrinsic-pragma"></a>intrinsic-Pragma

Gibt an, dass Funktionsaufrufe, die in der Argumentliste des Pragmas angegeben sind, systemintern sind.

## <a name="syntax"></a>Syntax

> **#pragma System intern (** *Funktion1* [ **,** _Funktion2_ ...] **)**

## <a name="remarks"></a>Hinweise

Das **intrinsische** Pragma weist den Compiler an, dass eine Funktion ein bekanntes Verhalten aufweist. Der Compiler kann die Funktion aufrufen und den Funktionsaufruf nicht durch Inlineanweisungen ersetzen, wenn dies zu einer besseren Leistung führt.

Die Bibliotheksfunktionen mit systeminternen Formularen werden nachfolgend aufgeführt. Sobald ein System internes Pragma angezeigt wird, tritt es mit der ersten Funktionsdefinition in Kraft, die eine bestimmte intrinsische Funktion enthält. Der Effekt wird bis zum Ende der Quelldatei oder bis zum Aussehen `function` eines Pragmas fortgesetzt, das die gleiche intrinsische Funktion angibt. Das **intrinsische** Pragma kann nur außerhalb einer Funktionsdefinition auf globaler Ebene verwendet werden.

Die folgenden Funktionen verfügen über intrinsische Formulare, und die systeminternen Formulare werden verwendet, wenn Sie [/Oi](../build/reference/oi-generate-intrinsic-functions.md)angeben:

|||||
|-|-|-|-|
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||

Programme, die intrinsische Funktionen verwenden, sind schneller, da Sie nicht über den Aufwand von Funktionsaufrufen verfügen, aber aufgrund des generierten zusätzlichen Codes möglicherweise größer werden.

**x86-spezifisch**

Die `_disable` System `_enable` internen Funktionen und generieren kernelmodusanweisungen, um Interrupts zu deaktivieren oder zu aktivieren, und könnten in Kernelmodustreibern nützlich sein.

### <a name="example"></a>Beispiel

Kompilieren Sie den folgenden Code über die Befehlszeile `cl -c -FAs sample.c` mit, und sehen Sie sich Sample. ASM an, um zu sehen, dass Sie sich in die x86-Anweisungen CLI und STI umwandeln

```cpp
// pragma_directive_intrinsic.cpp
// processor: x86
#include <dos.h>   // definitions for _disable, _enable
#pragma intrinsic(_disable)
#pragma intrinsic(_enable)
void f1(void) {
   _disable();
   // do some work here that should not be interrupted
   _enable();
}
int main() {
}
```

**End x86-spezifisch**

Die unten aufgeführten Gleit Komma Funktionen haben keine echten intrinsischen Formulare. Stattdessen verfügen sie über Versionen, die Argumente direkt an den Gleitkommachip übergeben, anstatt sie auf dem Programmstapel abzulegen:

|||||
|-|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)||

Die unten aufgeführten Gleit Komma Funktionen verfügen über echte intrinsische Formen, wenn Sie [/Oi](../build/reference/oi-generate-intrinsic-functions.md), [/og](../build/reference/og-global-optimizations.md)und [/fp: fast](../build/reference/fp-specify-floating-point-behavior.md) angeben (oder eine Option, die/OG: [/Ox](../build/reference/ox-full-optimization.md), [/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md)und [/O2](../build/reference/o1-o2-minimize-size-maximize-speed.md)umfasst):

|||||
|-|-|-|-|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)||||

Sie können [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) oder [/Za](../build/reference/za-ze-disable-language-extensions.md) verwenden, um die Generierung von echten systeminternen Gleit Komma Optionen zu überschreiben. In diesem Fall werden die Funktionen als Bibliotheksroutinen erzeugt, die Argumente direkt an den Gleitkommachip übergeben, statt sie auf dem Programmstapel abzulegen.

Informationen und ein Beispiel zum Aktivieren/Deaktivieren von systeminternen Funktionen für einen Quell Text Block finden Sie unter [#pragma-Funktion](../preprocessor/function-c-cpp.md) .

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
