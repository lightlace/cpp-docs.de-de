---
title: "intrinsic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "intrinsic_CPP"
  - "vc-pragma.intrinsic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "intrinsic-Pragma"
  - "Pragmas, intrinsic"
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# intrinsic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass Funktionsaufrufe, die in der Argumentliste des Pragmas angegeben sind, systemintern sind.  
  
## Syntax  
  
```  
  
#pragma intrinsic( function1 [, function2, ...] )  
```  
  
## Hinweise  
 Das **intrinsic**\-Pragma informiert den Compiler, dass eine Funktion ein bekanntes Verhalten aufweist.  Der Compiler kann die Funktion aufrufen und den Funktionsaufruf nicht durch Inlineanweisungen ersetzen, wenn dies zu einer besseren Leistung führt.  
  
 Die Bibliotheksfunktionen mit systeminternen Formularen werden nachfolgend aufgeführt.  Sobald ein **intrinsic**\-Pragma angezeigt wird, tritt es mit der ersten Funktionsdefinition in Kraft, die eine bestimmte systeminterne Funktion enthält.  Die Wirkung dauert bis zum Ende der Quelldatei oder bis zum Auftreten eines **function**\-Pragmas an, das die gleiche systeminterne Funktion angibt.  Das **intrinsic**\-Pragma kann nur außerhalb einer Funktionsdefinition auf globaler Ebene verwendet werden.  
  
 Die folgenden Funktionen haben systeminterne Formen und die systeminternen Formen werden verwendet, wenn Sie [\/Oi](../build/reference/oi-generate-intrinsic-functions.md) angeben:  
  
|||||  
|-|-|-|-|  
|[\_disable](../intrinsics/disable.md)|[\_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|  
|[\_enable](../intrinsics/enable.md)|[\_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../misc/labs-llabs.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|[\_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|[\_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||  
|[\_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[\_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||  
|[\_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||  
  
 Programme, die systeminterne Funktionen verwenden, sind schneller, da sie nicht den Mehraufwand der Funktionsaufrufe haben, sie können aufgrund des zusätzlich erstellten Codes jedoch größer sein.  
  
 **x86\-spezifisch**  
  
 Die systeminternen Funktionen \_disable und \_enable generieren Kernelmodusanweisungen, um Unterbrechungen zu deaktivieren bzw. aktivieren, und können in Kernelmodustreibern hilfreich sein.  
  
## Beispiel  
 Kompilieren Sie den folgenden Code in der Befehlszeile mit "cl \-c \-FAs sample.c", und überprüfen Sie sample.asm, um zu sehen, dass diese in x86\-Anweisungen CLI und STI umgewandelt werden:  
  
```  
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
  
 **x86\-spezifisch beenden**  
  
 Die unten aufgeführten Gleitkommafunktionen haben keine echten systeminternen Formen.  Stattdessen verfügen sie über Versionen, die Argumente direkt an den Gleitkommachip übergeben, anstatt sie auf dem Programmstapel abzulegen:  
  
|||||  
|-|-|-|-|  
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)||  
  
 Die unten aufgeführten Gleitkommafunktionen haben echte systeminterne Formen, wenn Sie [\/Oi](../build/reference/oi-generate-intrinsic-functions.md), [\/Og](../build/reference/og-global-optimizations.md) und [\/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) angeben \(oder eine Option, die \/Og: [\/Ox](../build/reference/ox-full-optimization.md), [\/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md) und \/O2 enthält\):  
  
|||||  
|-|-|-|-|  
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)||||  
  
 Sie können [\/fp:strict](../build/reference/fp-specify-floating-point-behavior.md) oder [\/Za](../build/reference/za-ze-disable-language-extensions.md) verwenden, um die Generierung von echten systeminternen Gleitkommaoptionen zu überschreiben.  In diesem Fall werden die Funktionen als Bibliotheksroutinen erzeugt, die Argumente direkt an den Gleitkommachip übergeben, statt sie auf dem Programmstapel abzulegen.  
  
 Weitere Informationen und ein Beispiel, wie systeminterne Funktionen für einen Block an Quelltext aktiviert\/deaktiviert werden, finden Sie unter [\# pragma\-Funktion](../preprocessor/function-c-cpp.md).  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)