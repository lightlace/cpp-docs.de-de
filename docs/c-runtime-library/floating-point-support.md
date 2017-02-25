---
title: "Gleitkommaunterst&#252;tzung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gleitkommazahlen"
  - "Gleitkommazahlen, Mathematische Routinen"
  - "Mathematische Routinen"
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Gleitkommaunterst&#252;tzung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Viele Microsoft\-Laufzeitbibliothekfunktionen erfordern Gleitkommaunterstützung von einem Mathematik\-Coprozessor oder von den Gleitkommabibliotheken, die zum Compiler gehören.  Die Funktionen zur Gleitkommaunterstützung werden nur bei Bedarf geladen.  
  
 Wenn Sie einen Gleitkomma\-Typspezifizierer in der Formatzeichenfolge eines Aufrufs einer Funktion in der Familie `printf` oder `scanf` verwenden, müssen Sie einen Gleitkommawert oder einen Zeiger auf einen Gleitkommawert in der Argumenteliste verwenden, um dem Compiler mitzuteilen, dass Gleitkommaunterstützung erforderlich ist.  
  
 Einen Beispielcode, der die Verarbeitung von Gleitkommaausnahmen zeigt, finden Sie unter [\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md).  
  
 Die Gleitkommapräzision von Zwischenwerten wird durch die Funktionen [\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) gesteuert.  Standardmäßig ist die Genauigkeitssteuerung in `_controlfp` auf 53 Bit \(\_PC\_53\) gesetzt.  Eine Verlinkung über FP10.OBJ ändert die Standard\-Genauigkeitssteuerung in 64 Bit \(\_PC\_64\).  In der Linker\-Befehlszeile muss FP10.OBJ vor LIBC.LIB, LIBCMT.LIB oder MSVCRT.LIB genannt sein.  
  
### Gleitkommafunktionen  
  
|Routine|Verwendung|.NET Framework\-Entsprechung|  
|-------------|----------------|----------------------------------|  
|[abs](../Topic/abs.md)|Rückgabe des absoluten Werts von `int`|[\<caps:sentence id\="tgt14" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[acos, acosf](../c-runtime-library/reference/acos-acosf-acosl.md)|Berechnung des Arcuscosinus|[\<caps:sentence id\="tgt17" sentenceid\="954a441495360a1fa8b0170297b2ff38" class\="tgtSentence"\>System::Math::Acos\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.acos.aspx)|  
|[asin, asinf](../c-runtime-library/reference/asin-asinf-asinl.md)|Berechnung des Arcussinus|[\<caps:sentence id\="tgt20" sentenceid\="313917cde9698a0924536719f5bece25" class\="tgtSentence"\>System::Math::Asin\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)|  
|[atan, atanf, atan2, atan2f](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Berechnung des Arcustangens|[System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan.aspx), [System::Math::Atan2](https://msdn.microsoft.com/en-us/library/system.math.atan2.aspx)|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Umwandeln einer Zeichenfolge in einen Gleitkommawert mit doppelter Genauigkeit|[System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx), [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[Bessel\-Funktionen](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Berechnen von Bessel\-Funktionen `_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_cabs](../c-runtime-library/reference/cabs.md)|Suchen des absoluten Werts einer komplexen Zahl|Nicht zutreffend.|  
|[cbrt](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|Berechnung der Kubikwurzel|Nicht zutreffend.|  
|[ceil, ceilf](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Suche nach einem ganzzahligen Höchstwert|[\<caps:sentence id\="tgt39" sentenceid\="656009d71fb974368bded363746de018" class\="tgtSentence"\>System::Math::Ceiling\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)|  
|[\_chgsign, \_chgsignf, \_chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|Umkehrung des Vorzeichens eines Gleitkommawerts mit doppelter Genauigkeit oder eines langen Gleitkommaarguments mit doppelter Genauigkeit|Nicht zutreffend.|  
|[\_clear87, \_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|Abrufen und Löschen des Gleitkommastatuswortes|Nicht zutreffend.|  
|[\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md), [\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|Aufruf des alten Gleitkommasteuerwortes und Festlegung des neuen Steuerwortwerts|Nicht zutreffend.|  
|[copysign, copysignf, copysignl, \_copysign, \_copysignf, \_copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|Rückgabe eines Werts mit dem Vorzeichen eines anderen Werts|Nicht zutreffend.|  
|[cos, cosf, cosh, coshf](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|Berechnung des Cosinus|[System::Math::Cos](https://msdn.microsoft.com/en-us/library/system.math.cos.aspx), [System::Math::Cosh](https://msdn.microsoft.com/en-us/library/system.math.cosh.aspx)|  
|[difftime](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|Berechnung der Differenz zwischen zwei angegebenen Zeitwerten|[\<caps:sentence id\="tgt54" sentenceid\="5f4f365a3cd7f368db2f6ce31b797fdf" class\="tgtSentence"\>System::DateTime::Subtract\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|  
|[div](../c-runtime-library/reference/div.md)|Teilen einer Ganzzahl durch eine andere und Rückgabe des Quotienten und des Rests|Nicht zutreffend.|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md), [\_ecvt\_s](../c-runtime-library/reference/ecvt-s.md)|Konvertieren von `double` in eine Zeichenfolge der angegebenen Länge|[\<caps:sentence id\="tgt60" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[exp, expf](../c-runtime-library/reference/exp-expf.md)|Berechnen einer Exponentialfunktion|[\<caps:sentence id\="tgt63" sentenceid\="81a65df6ac66cdc4a4b12c2f7e555487" class\="tgtSentence"\>System::Math::Exp\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)|  
|[fabs, fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Suche nach dem Absolutwert|[\<caps:sentence id\="tgt66" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[\_fcvt](../c-runtime-library/reference/fcvt.md), [\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|Konvertieren von `double` in eine Zeichenfolge mit einer angegebenen Anzahl von Ziffern hinter dem Dezimaltrennzeichen|[\<caps:sentence id\="tgt69" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_finite](../c-runtime-library/reference/finite-finitef.md)|Bestimmung, ob ein gegebener Gleitkommawert mit doppelter Genauigkeit endlich ist|[\<caps:sentence id\="tgt72" sentenceid\="8d081c50adeda3dde4cebab81a0b3583" class\="tgtSentence"\>System::Double::IsInfinity\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)|  
|[floor, floorf](../c-runtime-library/reference/floor-floorf-floorl.md)|Suche nach der größten Ganzzahl, die kleiner oder gleich dem Argument ist|[\<caps:sentence id\="tgt75" sentenceid\="609db9ab0433b647d5350d3b965d70f9" class\="tgtSentence"\>System::Math::Floor\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)|  
|[fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)|Suche nach dem Gleitkommarest|[\<caps:sentence id\="tgt78" sentenceid\="127a04426267ccb17fb4b566ad56de9c" class\="tgtSentence"\>System::Math::IEEERemainder\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)|  
|[\_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|Rückgabe des Statuswortes, das Information über die Gleitkommaklasse enthält|[System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx), [System::Double::IsNegativeInfinity](https://msdn.microsoft.com/en-us/library/system.double.isnegativeinfinity.aspx), [System::Double::IsPositiveInfinity](https://msdn.microsoft.com/en-us/library/system.double.ispositiveinfinity.aspx), [System::Double::IsNan](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)|Aufruf eines benutzerdefinierten Traphandlers für IEEE\-Gleitkommaausnahmen|Nicht zutreffend.|  
|[\_fpreset](../c-runtime-library/reference/fpreset.md)|Reinitialisieren eines mathematischen Gleitkommapakets||  
|[frexp](../c-runtime-library/reference/frexp.md)|Berechnen eines Exponentialwerts|Nicht zutreffend.|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md), [\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|Konvertieren von Gleitkommawerten in Zeichenfolgen|[\<caps:sentence id\="tgt92" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[hypot, hypotf, hypotl, \_hypot, \_hypotf, \_hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|Berechnung der Hypotenuse eines rechtwinkligen Dreiecks|Nicht zutreffend.|  
|[\_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|Prüfen eines Gleitkommawerts mit doppelter Genauigkeit für einen Nicht\-Zahlenwert \(NaN, Not a Number\)|[\<caps:sentence id\="tgt97" sentenceid\="18f7dc07d0c506c23f2f7eb89262d274" class\="tgtSentence"\>System::Double::IsNan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[labs](../misc/labs-llabs.md)|Rückgabe des absoluten Werts von `long`|[\<caps:sentence id\="tgt100" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[ldexp](../c-runtime-library/reference/ldexp.md)|Berechnung des Produkts aus einem Argument und 2<sup>exp</sup> \(bestimmte Potenz\)|[\<caps:sentence id\="tgt103" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[ldiv](../c-runtime-library/reference/ldiv-lldiv.md)|Teilen einer `long` Ganzzahl durch eine andere und Rückgabe des Quotienten und des Rests|Nicht zutreffend.|  
|[log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)|Berechnung eines natürlichen Logarithmus oder eines Logarithmus zur Basis 10.|[System::Math::Log](https://msdn.microsoft.com/en-us/library/system.math.log.aspx), [System::Math::Log10](https://msdn.microsoft.com/en-us/library/system.math.log10.aspx)|  
|[\_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|Extraktion des Exponentialwerts aus einem Gleitkommaargument mit doppelter Genauigkeit|Nicht zutreffend.|  
|[\_lrotl, \_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Verschiebung von `unsigned long int` nach links \(`_lrotl`\) oder rechts \(`_lrotr`\)|Nicht zutreffend.|  
|[\_matherr](../c-runtime-library/reference/matherr.md)|Behandlung von Mathematikfehlern|Nicht zutreffend.|  
|[\_\_max](../c-runtime-library/reference/max.md)|Rückgabe des größeren von zwei Werten|[\<caps:sentence id\="tgt121" sentenceid\="6f9dcb228534c3e5b0013615b2b1d003" class\="tgtSentence"\>System::Math::Max\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)|  
|[\_\_min](../c-runtime-library/reference/min.md)|Rückgabe des kleineren von zwei Werten|[\<caps:sentence id\="tgt124" sentenceid\="ff471983fc666dec7ba58b17a0bf76e6" class\="tgtSentence"\>System::Math::Min\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)|  
|[modf, modff](../c-runtime-library/reference/modf-modff-modfl.md)|Teilen eines Arguments in eine Ganzzahl und einen Bruch|Nicht zutreffend.|  
|[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Rückgabe eines stillen NaN\-Werts|[\<caps:sentence id\="tgt129" sentenceid\="c251043405ffa73fe857c83428b58fdc" class\="tgtSentence"\>System::Double::NaN\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.nan.aspx)|  
|[\_nextafter](../c-runtime-library/reference/nextafter-functions.md)|Rückgabe des nächsten darstellbaren Nachbarn|Nicht zutreffend.|  
|[pow, powf](../c-runtime-library/reference/pow-powf-powl.md)|Berechnung eines auf eine Potenz erhöhten Werts|[\<caps:sentence id\="tgt135" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Schreiben von Daten auf `stdout` in einem angegebenen Format|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx), [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)|  
|[rand](../c-runtime-library/reference/rand.md), [rand\_s](../c-runtime-library/reference/rand-s.md)|Aufruf einer Pseudozufallszahl|[\<caps:sentence id\="tgt141" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|Rundung auf die nächste Ganzzahl im Gleitkommaformat|[\<caps:sentence id\="tgt143" sentenceid\="1c04aeb4aeff1752cb65adabcee29f53" class\="tgtSentence"\>System::Math::Round\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)|  
|[\_rotl, \_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Verschiebung von `unsigned int` nach links \(`_rotl`\) oder rechts \(`_rotr`\)|Nicht zutreffend.|  
|[\_scalb](../c-runtime-library/reference/scalb.md)|Skalieren eines Arguments durch eine Zweierpotenz|Nicht zutreffend.|  
|[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|Multiplizieren mit einer ganzzahligen Potenz von `FLT_RADIX`|Nicht zutreffend.|  
|[scanf, wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Lesen von Daten aus `stdin` in einem angegebenen Format und Schreiben von Daten auf einen angegebenen Speicherort|[System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx), [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)|  
|[\_set\_controlfp](../c-runtime-library/reference/set-controlfp.md)|Festlegung des neuen Steuerwortwerts|Nicht zutreffend.|  
|[sin, sinf, sinh, sinhf](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|Berechnung des Sinus oder hyperbolischen Sinus|[System::Math::Sin](https://msdn.microsoft.com/en-us/library/system.math.sin.aspx), [System::Math::Sinh](https://msdn.microsoft.com/en-us/library/system.math.sinh.aspx)|  
|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Berechnung der Quadratwurzel|[\<caps:sentence id\="tgt162" sentenceid\="1a91af0bd8c63b4be64c7a0bec8dc8c4" class\="tgtSentence"\>System::Math::Sqrt\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)|  
|[srand](../c-runtime-library/reference/srand.md)|Initialisierung einer Pseudozufallsserie|[\<caps:sentence id\="tgt165" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[\_status87, \_statusfp, \_statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|Abrufen des Gleitkommastatuswortes|Nicht zutreffend.|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Umwandeln einer Zeichenfolge in einen Wert mit doppelter Genauigkeit|[\<caps:sentence id\="tgt169" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[tan, tanf, tanh, tanhf](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|Berechnung des Tangens oder des hyperbolischen Tangens|[System::Math::Tan](https://msdn.microsoft.com/en-us/library/system.math.tan.aspx), [System::Math::Tanh](https://msdn.microsoft.com/en-us/library/system.math.tanh.aspx)|  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)