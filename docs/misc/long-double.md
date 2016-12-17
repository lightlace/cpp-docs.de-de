---
title: "Long Double"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "c.types"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "10 Byte-Long Double"
  - "16-Bit Windows"
  - "32-Bit Windows"
  - "8-Byte-Long Double"
  - "80-Bit-Präzision"
  - "80-Bit-Präzision"
  - "8-Byte-Long Double"
  - "long double"
ms.assetid: bb581e20-b5c2-4079-8ee8-ac6739a37852
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Long Double
Vorherige 16\-Bit\-Versionen von Microsoft C\/C\+\+\- und Microsoft Visual C\+\+ unterstützten `long double`, Genauigkeitsdatentyp mit 80 Bits.  In Win32, das jedoch die `long double` Datentypzuordnungen zu `double`, 64\-Bit\-Genauigkeitsdatentyp Programmierung.  Die Microsoft\-Laufzeitbibliothek stellt `long double`\-Versionen der mathematischen Funktionen nur für die Abwärtskompatibilität bereit.  Die `long double` werden den Funktionsprototypen Prototypen für ihre `double` Entsprechungen identisch, dass der Datentyp `long``double` ersetzt den Datentyp `double`.  `long double` Die Versionen dieser Funktionen sollten nicht in neuen Code verwendet werden.  
  
### Doppelte Features und ihre langen doppelten Entsprechungen  
  
|Funktion|Langes Double<br /><br /> Entsprechung|Funktion|Langes Double<br /><br /> Entsprechung|  
|--------------|------------------------------------|--------------|------------------------------------|  
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|`acosl`|[frexp](../c-runtime-library/reference/frexp.md)|`frexpl`|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|`asinl`|[\_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|`_hypotl`|  
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|`atanl`|[ldexp](../c-runtime-library/reference/ldexp.md)|`ldexpl`|  
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|`atan2l`|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|`logl`|  
|[atof](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|`_atold`|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|`log10l`|  
|[Bessel\-Funktionen j0, j1, jn](../misc/bessel-functions-j0-j1-jn.md)|`j0l, j1l, jnl`|[\_matherr](../c-runtime-library/reference/matherr.md)|`_matherrl`|  
|[Bessel\-Funktionen YO, y1, yn](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|`y0l, y1l, ynl`|[modf](../c-runtime-library/reference/modf-modff-modfl.md)|`modfl`|  
|[\_cabs](../c-runtime-library/reference/cabs.md)|`_cabsl`|[pow](../c-runtime-library/reference/pow-powf-powl.md)|`powl`|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|`ceill`|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|`sinl`|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|`cosl`|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|`sinhl`|  
|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|`coshl`|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|`sqrtl`|  
|[exp](../c-runtime-library/reference/exp-expf.md)|`expl`|[strtod](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|`_strtold`|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|`fabsl`|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|`tanl`|  
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|`floorl`|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|`tanhl`|  
|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|`fmodl`|||  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)