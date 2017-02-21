---
title: "Gr&#246;&#223;enangabe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "printf-Funktion, Formatangabefelder"
ms.assetid: 525dc5d8-e70a-4797-a6a0-ec504a27355c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Gr&#246;&#223;enangabe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einer Formatspezifikation ist das vierte Feld ein Argumentlängenmodifizierer für den Konvertierungsspezifizierer.  Das Feld `size` fungiert als Präfix für das `type`\-Feld; `h`, `l`, `w`, `I`, `I32`, `I64` und `ll` geben je nach dem Konvertierungsspezifizierer, den sie ändern, die "Größe" des entsprechenden Arguments an: lang oder kurz, 32 Bit oder 64 Bit, Einzelbytezeichen oder Breitzeichen.  Diese Größenpräfixe werden zusammen mit `type`\-Zeichen in den Familien `printf` und `wprintf` der Funktionen verwendet, um der Interpretation von Argumentlängen gemäß der Darstellung in der folgenden Tabelle anzugeben.  Das `size`\-Feld ist für einige Argumenttypen optional.  Wenn kein Größenpräfix angegeben ist, konsumiert das Formatierungsprogramm ganzzahlige Argumente, z. B. `char`, `short`, `int`, `long` mit oder ohne Vorzeichen und Aufzählungstypen, wie etwa 32\-Bit `int`\-Typen, während Gleitkommaargumente als 64\-Bit\-`double`\-Typen konsumiert werden.  Dies stimmt mit den standardmäßigen Typerweiterungsregeln für Listen von Variablenargumenten überein.  Weitere Informationen zur Typerweiterung bei Argumenten finden Sie unter [Ellipsen und Standardargumente](../misc/ellipses-and-default-arguments.md).  Sowohl auf 32\-Bit als auch auf 64\-Bit\-Systemen muss die Formatbezeichnung eines ganzzahligen 64\-Bit\-Arguments das Größenpräfix `ll` oder `I64` beinhalten.  Andernfalls ist das Verhalten des Formatierungsprogramms nicht definiert.  
  
 Einige Typen weisen in 32\-Bit\- und 64\-Bit\-Code verschiedene Größen auf.  Beispielsweise ist `size_t` in für x86\-Systeme kompiliertem Code 32 Bit lang, bei Code für X64\-Systeme jedoch 64 Bit lang.  Zum Erstellen von plattformunabhängigem Formatierungscode für Typen mit variabler Breite können Sie einen Argumentlängenmodifizierer mit variabler Breite verwenden.  Verwenden Sie alternativ einen Argumentlängenmodifizierer mit 64\-Bit, und stufen Sie den Argumenttyp mit variabler Breite explizit auf 64 Bit herauf.  Der Microsoft\-spezifische Argumentlängenmodifizierer `I` verarbeitet Intergerargumente variabler Breite.  
  
> [!NOTE]
>  Die Längenmodifiziererpräfixe `I`, `I32` und `I64` sind Microsoft\-Erweiterungen und nicht ANSI\-kompatibel.  `h`\-Präfix zusammen mit Daten des Typs `char`, `w`\-Präfix zusammen mit Daten des Typs `wchar_t` und `l`\-Präfix zusammen mit Daten des Typs `double` sind Microsoft\-Erweiterungen.  Die Längenpräfixe `hh`, `j`, `z` und `t` werden nicht unterstützt.  
  
### Größenpräfix für die Formattypspezifizierer printf und wprintf  
  
|Angabe von|Präfix|Mit Typspezifizierer|  
|----------------|------------|--------------------------|  
|`long int`|`l` \(L als Kleinbuchstaben\)|`d`, `i`, `o`, `x` oder `X`|  
|`long unsigned int`|`l`|`o`, `u`, `x` oder `X`|  
|`long long`|`ll`|`d`, `i`, `o`, `x` oder `X`|  
|`short int`|`h`|`d`, `i`, `o`, `x` oder `X`|  
|`short unsigned int`|`h`|`o`, `u`, `x` oder `X`|  
|`__int32`|`I32`|`d`, `i`, `o`, `x` oder `X`|  
|`unsigned __int32`|`I32`|`o`, `u`, `x` oder `X`|  
|`__int64`|`I64`|`d`, `i`, `o`, `x` oder `X`|  
|`unsigned __int64`|`I64`|`o`, `u`, `x` oder `X`|  
|`ptrdiff_t` \(`__int32` auf 32\-Bit\-Plattformen, `__int64` auf 64\-Bit\-Plattformen\)|`I`|`d`, `i`, `o`, `x` oder `X`|  
|`size_t` \(`unsigned __int32` auf 32\-Bit\-Plattformen, `unsigned __int64` auf 64\-Bit\-Plattformen\)|`I`|`o`, `u`, `x` oder `X`|  
|`long double` \(Obwohl in [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]`long double` ein distinktiven Typ, hat er die gleiche interne Darstellung wie `double`.\)|`l` oder `L`|`a`, `A`, `e`, `E`, `f`, `g` oder `G`|  
|Einzelbytezeichen mit den Funktionen `printf` und `wprintf`.  \(Ein `hc`\- oder `hC`\-Typspezifizierer ist mit `c` in `printf`\-Funktionen und mit `C` in `wprintf`\-Funktionen synonym.\)|`h`|`c` oder `C`|  
|Breitzeichen mit den Funktionen `printf` und `wprintf`.  \(Ein `lc`\-, `lC`\-, `wc`\- oder `wC`\-Typspezifizierer ist mit `C` in `printf`\-Funktionen und mit `c` in `wprintf`\-Funktionen synonym.\)|`l` oder `w`|`c` oder `C`|  
|Einzelbytezeichenfolge mit den Funktionen `printf` und `wprintf`.  \(Ein `hs`\- oder `hS`\-Typspezifizierer ist mit `s` in `printf`\-Funktionen und mit `S` in `wprintf`\-Funktionen synonym.\)|`h`|`s`, `S` oder `Z`|  
|Breitzeichenfolge mit den Funktionen `printf` und `wprintf`.  \(Ein `ls`\-, `lS`\-, `ws`\- oder `wS`\-Typspezifizierer ist mit `S` in `printf`\-Funktionen und mit `s` in `wprintf`\-Funktionen synonym.\)|`l` oder `w`|`s`, `S` oder `Z`|  
  
## Siehe auch  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Flag\-Direktiven](../c-runtime-library/flag-directives.md)   
 [printf\-Breitenangabe](../c-runtime-library/printf-width-specification.md)   
 [Genauigkeitsangabe](../c-runtime-library/precision-specification.md)   
 [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md)