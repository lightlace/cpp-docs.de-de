---
title: Mathematische Unterstützung und Gleitkommaunterstützung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.math
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, math routines
- math routines
- floating-point numbers
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ddf4a6ce7e2ad98841c20fcef5fd9639a5797852
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="math-and-floating-point-support"></a>Mathematische Unterstützung und Gleitkommaunterstützung

Die universelle C-Laufzeitbibliothek (UCRT) stellt viele integrale Funktionen und Gleitkommafunktionen in der mathematischen Bibliothek bereit, einschließlich der laut ISO C99 erforderlichen Funktionen. Die Gleitkommafunktionen werden implementiert, damit die Leistung und Richtigkeit gleichwertig sichergestellt wird. Da das korrekt gerundete Ergebnis nur sehr teuer errechenbar ist, wurden diese Funktionen dazu entworfen, eine starke Annäherung an das korrekt gerundete Ergebnis zu erzielen. In den meisten Fällen liegt das erzeugte Ergebnis innerhalb von +/-1 an der letzten Nachkommastelle des korrekt gerundeten Ergebnisses, obwohl die Ungenauigkeit auch größer ausfallen kann.

Viele der Gleitkommafunktionen in der mathematischen Bibliothek haben unterschiedliche Implementierungen für verschiedene CPU-Architekturen. Die 32-Bit-x86-CRT hat möglicherweise eine andere Implementierung als die 64-Bit x64 CRT. Darüber hinaus haben möglicherweise einige der Funktionen mehrere Implementierungen für eine bestimmte CPU-Architektur. Eine möglichst effiziente Implementierung wird je nach den von der CPU unterstützten Anweisungssets dynamisch zur Laufzeit ausgewählt. In der 32-Bit-x86-CRT haben einige Funktionen eine x87- und eine SSE2-Implementierung. Wenn eine CPU verwendet wird, die SSE2 unterstützt, wird die schnellere SSE2-Implementierung verwendet. Wenn eine CPU verwendet wird, die SSE2 nicht unterstützt, wird die langsamere x87-Implementierung verwendet. Da verschiedene Implementierungen der Funktionen der mathematischen Bibliothek verschiedene CPU-Anweisungen und andere Algorithmen verwenden, um Ergebnisse zu erzielen, unterscheiden sich die Ergebnisse in den verschiedenen CPUs möglicherweise. In den meisten Fällen liegen die Ergebnisse innerhalb +/-1 ULP des korrekt gerundeten Ergebnisses, die tatsächlichen Ergebnisse können jedoch in den CPUs variieren.

16-Bit-Vorgängerversionen von Microsoft C/C++ und Microsoft Visual C++ unterstützten den Typ **long double** als einen 80-Bit-präziser Gleitkomma-Datentyp. In späteren Versionen von Visual C++ ist der **long double**-Datentyp ein 64-Bit-präziser Gleitkomma-Datentyp, der identisch mit Typ **double** ist. Der Compiler behandelt **long double** und **double** als unterschiedliche Typen. Die **long double**-Funktionen stimmen jedoch mit ihren **double**-Gegenstücken überein. Die CRT stellt **long double**-Versionen der mathematischen Funktionen für die ISO C99-Quellcodekompatibilität bereit. Beachten Sie aber, dass die binäre Darstellung von anderen Compilern abweichen kann.

## <a name="supported-math-and-floating-point-routines"></a>Unterstützte mathematische und Gleitkommaroutinen

|-Routine zurückgegebener Wert|Mit|
|-|-|
[abs, labs, llabs, _abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Berechnet den absoluten Wert eines Ganzzahltyps
[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|Berechnet den Arkuskosinus
[acosh, acoshf, acoshl](../c-runtime-library/reference/acosh-acoshf-acoshl.md)|Berechnet den hyperbolischen Arkuskosinus
[asin, asinf, asinl](../c-runtime-library/reference/asin-asinf-asinl.md)|Berechnet den Arkussinus
[asinh, asinhf, asinhl](../c-runtime-library/reference/asinh-asinhf-asinhl.md)|Berechnet den hyperbolischen Arkussinus
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Berechnet den Arkustangens
[atanh, atanhf, atanhl](../c-runtime-library/reference/atanh-atanhf-atanhl.md)|Berechnet den hyperbolischen Arkustangens
[_atodbl, _atodbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Konvertiert eine gebietsschemaspezifische Zeichenfolge in einen **double**-Wert
[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Konvertiert eine Zeichenfolge in einen **double**-Wert
[_atoflt, _atoflt_l, _atoldbl, _atoldbl_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Konvertiert eine gebietsschemaspezifische Zeichenfolge in einen **float**- oder **long double**-Wert
[cbrt, cbrtf, cbrtl](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|Berechnet die Kubikwurzel
[ceil, ceilf, ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Berechnet den Höchstwert
[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|Berechnet das additive Inverse (Gegenzahl)
[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|Ruft das Gleitkommastatusregister ab und löscht dieses
[_control87, \__control87_2, _controlfp](../c-runtime-library/reference/control87-controlfp-control87-2.md)|Ruft das Gleitkommasteuerwort ab und legt es fest.
[_controlfp_s](../c-runtime-library/reference/controlfp-s.md)|Eine sicherere Version von **_controlfp**
[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|Gibt einen Wert zurück, der die Größe eines Arguments und das Zeichen eines anderen Arguments aufweist
[cos, cosf, cosl](../c-runtime-library/reference/cos-cosf-cosl.md)|Berechnet den Sinus
[cosh, coshf, coshl](../c-runtime-library/reference/cosh-coshf-coshl.md)|Berechnet den hyperbolischen Sinus
[div, ldiv, lldiv](../c-runtime-library/reference/div.md)|Berechnet den Quotienten und den Rest von zwei ganzzahligen Werten
[_ecvt](../c-runtime-library/reference/ecvt.md), [ecvt](../c-runtime-library/reference/posix-ecvt.md)|Konvertiert einen **double**-Wert in eine Zeichenfolge
[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Eine sicherere Version von **_ecvt**
[erf, erff, erfl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Berechnet die Fehlerfunktion
[erfc, erfcf, erfcl](../c-runtime-library/reference/erf-erff-erfl-erfc-erfcf-erfcl.md)|Berechnet die komplementäre Fehlerfunktion
[exp, expf, expl](../c-runtime-library/reference/exp-expf.md)|Berechnet den exponentiellen Wert *e*<sup>x</sup>
[exp2, exp2f, exp2l](../c-runtime-library/reference/exp2-exp2f-exp2l.md)|Berechnet den exponentiellen Wert 2<sup>x</sup>
[expm1, expm1f, expm1l](../c-runtime-library/reference/expm1-expm1f-expm1l.md)|Berechnet *e*<sup>x</sup>-1
[fabs, fabsf, fabsl](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Berechnet den absoluten Wert eines Gleitkommatyps
[_fcvt](../c-runtime-library/reference/fcvt.md), [fcvt](../c-runtime-library/reference/posix-fcvt.md)|Konvertiert eine Gleitkommazahl in eine Zeichenfolge
[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Eine sicherere Version von **_fcvt**
[fdim, fdimf, fdiml](../c-runtime-library/reference/fdim-fdimf-fdiml.md)|Bestimmt den positiven Unterschied zwischen zwei Werten
[feclearexcept](../c-runtime-library/reference/feclearexcept1.md)|Löscht die angegebenen Gleitkommaausnahmen
[fegetenv](../c-runtime-library/reference/fegetenv1.md)|Speichert die aktuelle Gleitkommaausnahme
[fegetexceptflag](../c-runtime-library/reference/fegetexceptflag2.md)|Ruft den Status der angegebenen Gleitkommaausnahme ab
[fegetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Ruft den Rundungsmodus des Gleitkommas ab
[feholdexcept](../c-runtime-library/reference/feholdexcept2.md)|Legt den ununterbrochenen Modus der Gleitkommaausnahme fest
[feraiseexcept](../c-runtime-library/reference/feraiseexcept.md)|Löst die angegebenen Gleitkommaausnahmen aus
[fesetenv](../c-runtime-library/reference/fesetenv1.md)|Legt die aktuelle Gleitkommaumgebung fest
[fesetexceptflag](../c-runtime-library/reference/fesetexceptflag2.md)|Legt die angegebenen Gleitkomma-Statusflags fest
[fesetround](../c-runtime-library/reference/fegetround-fesetround2.md)|Legt den angegebenen Rundungsmodus des Gleitkommas fest
[fetestexcept](../c-runtime-library/reference/fetestexcept1.md)|Bestimmt, welche Gleitkommaausnahme-Statusflags festgelegt werden
[feupdateenv](../c-runtime-library/reference/feupdateenv.md)|Stellt eine Gleitkommaumgebung wieder her und löst dann vorherige Ausnahmen aus
[_finite, _finitef](../c-runtime-library/reference/finite-finitef.md)|Bestimmt, ob ein Wert endlich ist
[floor, floorf, floorl](../c-runtime-library/reference/floor-floorf-floorl.md)|Berechnet den Tiefstwert
[fma, fmaf, fmal](../c-runtime-library/reference/fma-fmaf-fmal.md)|Berechnet eine Fused-multiply-add-Operation
[fmax, fmaxf, fmaxl](../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)|Berechnet die maximale Anzahl der Argumente
[fmin, fminf, fminl](../c-runtime-library/reference/fmin-fminf-fminl.md)|Berechnet die minimale Anzahl der Argumente
[fmod, fmodf, fmodl](../c-runtime-library/reference/fmod-fmodf.md)|Berechnet den Gleitkommarest
[_fpclass, _fpclassf](../c-runtime-library/reference/fpclass-fpclassf.md)|Gibt die Klassifizierung eines Gleitkommawerts zurück
[fpclassify](../c-runtime-library/reference/fpclassify.md)|Gibt die Klassifizierung eines Gleitkommawerts zurück
[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|Legt einen Handler für Gleitkommaausnahmen fest
[_fpreset](../c-runtime-library/reference/fpreset.md)|Setzt die Gleitkommaumgebung zurück
[frexp, frexpf, frexpl](../c-runtime-library/reference/frexp.md)|Ruft die Mantisse und den Exponenten einer Gleitkommazahl ab
[_gcvt](../c-runtime-library/reference/gcvt.md), [gcvt](../c-runtime-library/reference/posix-gcvt.md)|Konvertiert eine Gleitkommazahl in eine Zeichenfolge
[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Eine sicherere Version von **_gcvt**
[_get_FMA3_enable, _set_FMA3_enable](../c-runtime-library/reference/get-fma3-enable-set-fma3-enable.md)|Ruft ein Flag für die Verwendung von FMA3-Anweisungen auf x64 ab, oder legt es fest
[hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|Berechnet die Hypotenuse
[ilogb, ilogbf, ilogbl](../c-runtime-library/reference/ilogb-ilogbf-ilogbl2.md)|Berechnet den ganzzahligen Exponenten zur Basis 2
[imaxabs](../c-runtime-library/reference/imaxabs.md)|Berechnet den absoluten Wert eines Ganzzahltyps
[imaxdiv](../c-runtime-library/reference/imaxdiv.md)|Berechnet den Quotienten und den Rest von zwei ganzzahligen Werten
[isnan, _isnan, _isnanf](../c-runtime-library/reference/isnan-isnan-isnanf.md)|Testet einen Gleitkommawert auf NaN
[_j0, _j1, _jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Berechnet die Bessel-Funktion
[ldexp, ldexpf, ldexpl](../c-runtime-library/reference/ldexp.md)|Berechnet x*2<sup>n</sup>
[lgamma, lgammaf, lgammal](../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)|Berechnet den natürlichen Logarithmus des absoluten Werts der Gammafunktion
[llrint, llrintf, llrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Rundet einen Gleitkommawert auf den nächsten Wert von **long long**
[llround, llroundf, llroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Rundet einen Gleitkommawert auf den nächsten Wert von **long long**
[log, logf, logl, log10, log10f, log10l](../c-runtime-library/reference/log-logf-log10-log10f.md)|Berechnet den natürlichen Logarithmus oder den Logarithmus zur Basis 10
[log1p, log1pf, log1pl](../c-runtime-library/reference/log1p-log1pf-log1pl2.md)|Berechnet den natürlichen Logarithmus von 1+x
[log2, log2f, log2l](../c-runtime-library/reference/log2-log2f-log2l.md)|Berechnet den Logarithmus zur Basis 2
[logb, logbf, logbl, _logb, _logbf](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|Gibt den Exponenten eines Gleitkommawerts zurück
[lrint, lrintf, lrintl](../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)|Rundet einen Gleitkommawert auf den nächsten Wert von **long**
[_lrotl, _lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Rotiert einen ganzzahligen Wert nach links oder rechts
[lround, lroundf, lroundl](../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)|Rundet einen Gleitkommawert auf den nächsten Wert von **long**
[_matherr](../c-runtime-library/reference/matherr.md)|Der Standardhandler für mathematische Fehler
[__max](../c-runtime-library/reference/max.md)|Ein Makro, das den größeren von zwei Werten zurückgibt
[__min](../c-runtime-library/reference/min.md)|Ein Makro, das den kleineren von zwei Werten zurückgibt
[modf, modff, modfl](../c-runtime-library/reference/modf-modff-modfl.md)|Teilt einen Gleitkommawert in Nachkommastellen und ganze Zahlen
[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Gibt einen stillen NaN-Wert zurück.
[nearbyint, nearbyintf, nearbyintl](../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)|Gibt den gerundeten Wert zurück
[nextafter, nextafterf, nextafterl, _nextafter, _nextafterf](../c-runtime-library/reference/nextafter-functions.md)|Gibt den nächsten darstellbaren Gleitkommawert zurück
[nexttoward, nexttowardf, nexttowardl](../c-runtime-library/reference/nextafter-functions.md)|Gibt den nächsten darstellbaren Gleitkommawert zurück
[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)|Gibt den Wert von *x*<sup>*y*</sup> zurück
[remainder, remainderf, remainderl](../c-runtime-library/reference/remainder-remainderf-remainderl.md)|Berechnet den Rest des Quotienten aus zwei Gleitkommawerten
[remquo, remquof, remquol](../c-runtime-library/reference/remquo-remquof-remquol.md)|Berechnet den Rest von zwei ganzzahligen Werten
[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|Rundet einen Gleitkommawert
[_rotl, _rotl64, _rotr, _rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Rotiert Bits in ganzzahligen Typen
[round, roundf, roundl](../c-runtime-library/reference/round-roundf-roundl.md)|Rundet einen Gleitkommawert
[_scalb, _scalbf](../c-runtime-library/reference/scalb.md)|Skaliert das Argument mit einer Zweierpotenz
[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|Multipliziert eine Gleitkommazahl mit einer integralen Potenz von **FLT_RADIX**
[_set_controlfp](../c-runtime-library/reference/set-controlfp.md)|Legt das Gleitkommasteuerwort fest
[_set_SSE2_enable](../c-runtime-library/reference/set-sse2-enable.md)|Aktiviert oder deaktiviert SSE2-Anweisungen
[sin, sinf, sinl](../c-runtime-library/reference/sin-sinf-sinl.md)|Berechnet den Sinus
[sinh, sinhf, sinhl](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Berechnet den hyperbolischen Sinus
[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Berechnet die Quadratwurzel
[_status87, _statusfp, _statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|Ruft das Gleitkommastatuswort ab
[strtof, _strtof_l](../c-runtime-library/reference/strtof-strtof-l-wcstof-wcstof-l.md)|Konvertiert eine Zeichenfolge in einen **float**-Wert.
[strtold, _strtold_l](../c-runtime-library/reference/strtold-strtold-l-wcstold-wcstold-l.md)|Konvertiert eine Zeichenfolge in einen Wert von **long** **double**
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)|Berechnet den Tangens
[tanh, tanhf, tanhl](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Berechnet den hyperbolischen Tangens
[tgamma, tgammaf, tgammal](../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)|Berechnet die Gammafunktion
[trunc, truncf, truncl](../c-runtime-library/reference/trunc-truncf-truncl.md)|Verkürzt die Nachkommastellen
[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Konvertiert eine breite Zeichenfolge in einen **double**-Wert
[_y0, _y1, _yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Berechnet die Bessel-Funktion

## <a name="see-also"></a>Siehe auch

[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
