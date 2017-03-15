---
title: "Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcstoui64"
  - "_tcstoi64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Analysieren, Numerische Zeichenfolgen"
  - "Zeichenfolgenkonvertierung, zu numerischen Werten"
ms.assetid: 11cbd9ce-033b-4914-bf66-029070e7e385
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

-   [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)  
  
-   [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)  
  
-   [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)  
  
-   [\_strtoi64, \_wcstoi64, \_strtoi64\_l, \_wcstoi64\_l](../c-runtime-library/reference/strtoi64-wcstoi64-strtoi64-l-wcstoi64-l.md)  
  
-   [\_strtoui64, \_wcstoui64, \_strtoui64\_l, \_wcstoui64\_l](../c-runtime-library/reference/strtoui64-wcstoui64-strtoui64-l-wcstoui64-l.md)  
  
## Hinweise  
 Jede Funktion in der Gruppe **strtod**  konvertiert eine auf NULL abschließende Zeichenfolge in einen numerischen Wert.  Die verfügbaren Features sind in der folgenden Tabelle aufgeführt.  
  
|Funktion|**Beschreibung**|  
|--------------|----------------------|  
|`strtod`|Bekehrtzeichenfolge Gleitkommawert mit doppelter Genauigkeit|  
|`strtol`|Bekehrtzeichenfolge der lange ganze Zahl|  
|`strtoul`|Bekehrtzeichenfolge lange ganze Zahl ohne Vorzeichen|  
|`_strtoi64`|Bekehrtzeichenfolge in 64\-Bit\- `__int64` ganze Zahl|  
|`_strtoui64`|Bekehrtzeichenfolge in 64\-Bit\- `__int64` ganze Zahl ohne Vorzeichen|  
  
 `wcstod`, `wcstol`, `wcstoul` und `_wcstoi64` sind Breitzeichenversionen von `strtod`, `strtol`, `strtoul` und `_strtoi64`, verwendet.  Das Zeichenfolgenargument zu jeder dieser Breitzeichenfunktionen ist eine Zeichenfolge mit Breitzeichen; jede Funktion verhält sich genauso wie der Einzelbytezeichenentsprechung andernfalls.  
  
 Die `strtod`\-Funktion akzeptiert zwei Argumente: das erste ist die Eingabezeichenfolge und das zweite ein Zeiger auf Zeichen, das den Umgang beendet.  `strtol`, `strtoul`, **\_strtoi64**  und **\_strtoui64**  verwenden ein drittes Argument als Basis zur Verwendung im Konvertierungsprozess.  
  
 Die Eingabezeichenfolge ist eine Sequenz von Zeichen, die als numerischer Wert des angegebenen Typs interpretiert werden.  Jede Funktion beendet, die Zeichenfolge am ersten Zeichen lesen, das nicht als Teil einer Zahl erkennen kann.  Dies ist möglicherweise das beendende NULL\-Zeichen.  Für `strtol`, `strtoul`, `_strtoi64` und `_strtoui64` kann dieses und Endzeichen das erste numerische Zeichen größer oder gleich der vom Benutzer bereitgestellte Basis auch sein.  
  
 Wenn der vom Benutzer bereitgestellte Zeiger zu einem Ende\-vonKonvertierungszeichen nicht auf **NULL**  an der Gesprächszeit festgelegt, wird ein Zeiger auf Zeichen, das die Überprüfung abgeschlossen, dort stattdessen gespeichert.  Wenn keine Konvertierung ausgeführt werden kann \(keine gültigen Ziffern gefunden wurden, oder eine unzulässige Basis wurde angegeben\), wird der Wert des Zeichenfolgenzeigers an diese Adresse gespeichert.  
  
 `strtod` erwartet eine Zeichenfolge der folgenden Form:  
  
 \[*Leerzeichen*\] \[*Vorzeichen*\] \[`digits`\] \[**.**`digits`\] \[ {**d** &#124; **D** &#124; **e** &#124; **E**}\[*Vorzeichen*\]`digits`\]  
  
 *Leerräume* bestehen möglicherweise Leerzeichen oder aus Tabstoppzeichen, die ignoriert; *Vorzeichen* ist entweder Pluszeichen \(**\+**\) oder Minuszeichen \(**–**\); und `digits` sind eine oder mehrere Dezimalstellen.  Wenn keine Ziffern vor dem Basiszeichen stehen, muss mindestens eine Ziffer nach dem Basiszeichen stehen.  Die Dezimalstellen können von einem Exponenten folgen, der einführenden einem Buchstaben \(**d**, **D**, **e** oder **E**\) und optional aus einer Zahl mit Vorzeichen besteht.  Wenn weder ein Exponententeil noch ein Basiszeichen angezeigt wird, wird davon ausgegangen, dass ein Basiszeichen auf die letzte Ziffer in der Zeichenfolge folgt.  Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung.  
  
 `strtol`, `strtoul`, `_strtoi64` und `_strtoui64`\-Funktionen wird erwartet eine Zeichenfolge der folgenden Form:  
  
 \[*Leerzeichen*\] \[{**\+** &#124; **–**}\] \[**0** \[{ **w** &#124; **X** }\]\] \[`digits`\]  
  
 Wenn das Basisarray Argument zwischen 2 und 36 ist, wird es während Basis der Zahl verwendet.  Wenn es 0 ist, werden die ersten Zeichen, die auf der Ende\-vonKonvertierungszeiger verwiesen wird, verwendet, um die Basisklasse zu bestimmen.  Wenn das erste Zeichen 0 ist und das zweite Zeichen nicht "x" und "X" ist, wird die Zeichenfolge als ganze Oktalzahl interpretiert; Andernfalls wird es als Dezimalzahl interpretiert.  Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert.  Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert.  Der Buchstabe" bis "z" \(oder "A" bis "Z "\) werden die Werte 10 bis 35 zugewiesen; nur Buchstaben, deren spezifische Werte kleiner sind, als *Basisklasse* sind zulässig.  `strtoul` und `_strtoui64` ermöglichen einem Pluszeichen \(**\+**\) oder Minuszeichen \(des \-\-\) Zeichenpräfixes; ein führendes Minuszeichen gibt an, dass der Rückgabewert negiert wird.  
  
 Der Ausgabewert ist von der `LC_NUMERIC`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das **\_l**\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **\_l**\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  
  
 Als der Wert, der durch diese Funktionen zurückgegeben wurde, einen Überlauf oder Unterlauf einen verursacht wird oder wenn die Konvertierung nicht möglich ist, werden Sonderfallwerte wie dargestellt zurückgegeben:  
  
|Funktion|Bedingung|Zurückgegebener Wert|  
|--------------|---------------|--------------------------|  
|`strtod`|Overflow|\+\/\- `HUGE_VAL`|  
|`strtod`|Unterlauf oder keine Konvertierung|0|  
|`strtol`|\+ Überlauf|**LONG\_MAX**|  
|`strtol`|Überlauf \-|**LONG\_MIN**|  
|`strtol`|Unterlauf oder keine Konvertierung|0|  
|`_strtoi64`|\+ Überlauf|**\_I64\_MAX**|  
|`_strtoi64`|Überlauf \-|**\_I64\_MIN**|  
|`_strtoi64`|Keine Konvertierung|0|  
|`_strtoui64`|Overflow|**\_UI64\_MAX**|  
|`_strtoui64`|Keine Konvertierung|0|  
  
 \_**\_I64\_MAX**,**I64\_MIN** und  **\_UI64\_MAX** werden in LIMITS.H. definiert.  
  
 `wcstod`, `wcstol`, `wcstoul`, `_wcstoi64` und `_wcstoui64` sind Breitzeichenversionen von `strtod`, `strtol`, `strtoul`, `_strtoi64` und `_strtoui64`, verwendet; der Zeiger zu einem Ende\-vonKonvertierungsargument zu jeder dieser Breitzeichenfunktionen ist eine Zeichenfolge mit Breitzeichen.  Andernfalls verhält sich jede dieser Breitzeichenfunktionen identisch mit der Einzelbytezeichenentsprechung.  
  
## Siehe auch  
 [Datenkonvertierung](../c-runtime-library/data-conversion.md)   
 [Locale](../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Gleitkommaunterstützung](../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)