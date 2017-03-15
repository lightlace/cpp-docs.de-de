---
title: "printf-Typenfeldzeichen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "printf-Funktion, Formatangabefelder"
  - "printf-Funktion, Typenfeldzeichen"
ms.assetid: 699cb438-cd14-402e-9f81-c7a32acc3317
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# printf-Typenfeldzeichen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einer Formatangabe ist das `type`\-Zeichen ein Konvertierungsspezifizierer, der angibt, ob das entsprechende Argument als Zeichen, Zeichenfolge, Zeiger, ganze Zahl oder Gleitkommazahl interpretiert werden soll.  Das `type`\-Zeichen ist das einzige erforderliche Formatangabenfeld und erscheint nach allen optionalen Feldern.  
  
 Die Argumente, die der Formatzeichenfolge folgen, werden nach dem entsprechenden `type`\-Zeichen und dem optionalen Präfix [Größe](../c-runtime-library/size-specification.md) interpretiert.  Konvertierungen für die Zeichentypen `char` und `wchar_t` werden durch `c` oder `C` angegeben, und Einzelbyte\- und Multibyte\- oder Breitzeichen\-Zeichenfolgen werden je nach zu benötigter Formatierungsfunktion durch `s`oder `S` angegeben.  Zeichen und Zeichenfolgenargumente, die durch `c` und `s` angegeben werden, werden von den `printf`\-Familienfunktionen als `char` und `char*` oder von den `wprintf`\-Familienfunktionen als `wchar_t` und `wchar_t*` interpretiert.  Zeichen und Zeichenfolgenargumente, die durch `C` und `S` angegeben werden, werden von den `printf`\-Familienfunktionen als `wchar_t` und `wchar_t*` oder von den `wprintf`\-Familienfunktionen als `char` und `char*` interpretiert.  
  
 Ganzzahlige Typen wie `short`, `int`, `long`, `long long` und ihre `unsigned`\-Varianten werden durch `d`, `i`, `o`, `u`, `x`, und `X` angegeben.  Gleitkommatypen wie `float`, `double` und `long double` werden durch `a`, `A`, `e`, `E`, `f`, `g` und `G` angegeben.  Sofern Sie nicht durch ein `size`\-Feldlängenpräfix geändert werden, werden ganzzahlige Argumente standardmäßig in den `int`\-Typ umgewandelt. Gleitkommaargumente werden in `double` umgewandelt.  Bei 64\-Bit\-Systemen ist `int` ein 32\-Bit\-Wert. Daher werden ganze 64\-Bit\-Zahlen verkürzt, wenn sie für Ausgabe formatiert werden, sofern nicht ein `size`\-Präfix von `ll` oder `I64` verwendet wird.  Durch `p` angegebene Zeigertypen verwenden die Standardlänge für die Plattform.  
  
> [!NOTE]
>  Die `C`\-, `S`\- und `Z`\-Typzeichen sowie das Verhalten der `c`\- und `s`\-Typzeichen stellen bei Verwendung mit `printf`\- und `wprintf`\-Funktionen Microsoft\-Erweiterungen dar und sind nicht ANSI\-kompatibel.  Das `F`\-Typzeichen wird von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] nicht unterstützt.  
  
### printf\-Typenfeldzeichen  
  
|Typzeichen|Argument|Ausgabeformat|  
|----------------|--------------|-------------------|  
|`c`|Zeichen|Gibt bei Verwendung mit `printf`\-Funktionen ein Einzelbytezeichen und bei Verwendung mit `wprintf`\-Funktionen ein Breitzeichen an.|  
|`C`|Zeichen|Gibt bei Verwendung mit `printf`\-Funktionen ein Breitzeichen und bei Verwendung mit `wprintf`\-Funktionen ein Einzelbytezeichen an.|  
|`d`|Integer|Ganze Dezimalzahl mit Vorzeichen|  
|`i`|Integer|Ganze Dezimalzahl mit Vorzeichen|  
|`o`|Integer|Oktale ganze Zahl ohne Vorzeichen|  
|`u`|Integer|Ganze Dezimalzahl ohne Vorzeichen|  
|`x`|Integer|Ganze Hexadezimalzahl ohne Vorzeichen; verwendet „abcdef“.|  
|`X`|Integer|Ganze Hexadezimalzahl ohne Vorzeichen; verwendet „ABCDEF“.|  
|`e`|Gleitkomma|Wert mit Vorzeichen im Format \[\-\]\[ – \]`d`**.**`dddd` e \[*Vorzeichen*\]`dd[d]`, wobei `d` eine Dezimalzahl ist, `dddd` eine oder mehrere Dezimalstellen sind, `dd[d]` je nach [Ausgabeformat](../c-runtime-library/set-output-format.md) und Exponentengröße zwei oder drei Dezimalstellen sind und *Vorzeichen* „\+“ oder „–“ ist.|  
|`E`|Gleitkomma|Identisch mit dem `e`\-Format mit der Ausnahme, dass **E** anstelle von **e** den Exponenten einführt.|  
|`f`|Gleitkomma|Wert mit Vorzeichen im Format \[ – \]`dddd`**.**`dddd`, wobei `dddd` eine oder mehrere Dezimalstellen sind.  Die Anzahl der Ziffern vor dem Dezimaltrennzeichen ist abhängig von der Größe der Zahl, und die Anzahl der Ziffern nach dem Dezimaltrennzeichen ist abhängig von der angeforderten Genauigkeit.|  
|`g`|Gleitkomma|Werte mit Vorzeichen werden im `f`\- oder `e`\-Format angezeigt, je nachdem, was für den angegebenen Wert und die Genauigkeit kompakter ist.  Das `e`\-Format wird nur verwendet, wenn der Exponent des Werts kleiner als \-4 oder größer als oder gleich dem `precision`\-Argument ist.  Nachfolgende Nullen werden abgeschnitten, und das Dezimaltrennzeichen wird nur angezeigt, wenn eine oder mehrere Ziffern darauf folgen.|  
|`G`|Gleitkomma|Identisch mit dem `g`\-Format mit der Ausnahme, dass **E** anstelle von **e** den Exponenten einführt \(falls zutreffend\).|  
|`a`|Gleitkomma|Hexadezimaler Gleitkommawert mit doppelter Genauigkeit mit Vorzeichen im Format \[−\]0x*h.hhhh* **p±**`dd`, wobei *h.hhhh* die hexadezimalen Ziffern \(in Kleinbuchstaben\) der Mantisse und `dd` eine oder mehrere Ziffern für den Exponenten sind.  Die Genauigkeit gibt die Anzahl der Ziffern nach dem Punkt an.|  
|`A`|Gleitkomma|Hexadezimaler Gleitkommawert mit doppelter Genauigkeit mit Vorzeichen im Format \[−\]0X*h.hhhh* **P±**`dd`, wobei *h.hhhh* die hexadezimalen Ziffern \(in Großbuchstaben\) der Mantisse und `dd` eine oder mehrere Ziffern für den Exponenten sind.  Die Genauigkeit gibt die Anzahl der Ziffern nach dem Punkt an.|  
|`n`|Zeiger auf eine ganze Zahl|Anzahl der Zeichen, die bisher erfolgreich in den Stream oder Puffer geschrieben wurden.  Dieser Wert wird in der ganzen Zahl gespeichert, deren Adresse als Argument angegeben ist.  Weitere Informationen finden unter „Sicherheitshinweis“ weiter unten in diesem Artikel.|  
|`p`|Zeigertyp|Zeigt das Argument als Adresse in Hexadezimalziffern an.|  
|`s`|Zeichenfolge|Gibt bei Verwendung mit `printf`\-Funktionen eine Einzelbyte\- oder Multibyte\-Zeichenfolge und bei Verwendung mit `wprintf`\-Funktionen eine Breitzeichenfolge an.  Zeichen werden bis zum ersten NULL\-Zeichen oder bis zum `precision`\-Wert angezeigt.|  
|`S`|Zeichenfolge|Gibt bei Verwendung mit `printf`\-Funktionen eine Breitzeichenfolge und bei Verwendung mit `wprintf`\-Funktionen eine Einzelbyte\- oder Multibyte\-Zeichenfolge an.  Zeichen werden bis zum ersten NULL\-Zeichen oder bis zum `precision`\-Wert angezeigt.|  
|`Z`|`ANSI_STRING`\- oder `UNICODE_STRING`\-Struktur|Wenn die Adresse einer [ANSI\_STRING](http://msdn.microsoft.com/library/windows/hardware/ff540605.aspx)\- oder [UNICODE\_STRING](http://msdn.microsoft.com/library/windows/hardware/ff564879.aspx)\-Struktur als Argument übergeben wird, wird die Zeichenfolge angezeigt, die im Puffer enthalten ist, auf den mit dem `Buffer`\-Feld der Struktur gezeigt wird.  Verwenden Sie ein Längenpräfix von `w`, um ein `UNICODE_STRING`\-Argument anzugeben, z. B. `%wZ`.  Das `Length`\-Feld der Struktur muss auf die Länge der Zeichenfolge in Bytes festgelegt sein.  Das `MaximumLength`\-Feld der Struktur muss auf die Länge des Puffers in Bytes festgelegt sein.<br /><br /> In der Regel wird das `Z`\-Typzeichen nur in Treiberdebugfunktionen mit einer Formatangabe verwendet, z. B. `dbgPrint` und `kdPrint`.|  
  
 Wenn das Argument, das einem Gleitkomma\-Konvertierungsspezifizierer entspricht, unendlich, unbestimmt oder NAN ist, wird in der folgenden Tabelle die formatierte Ausgabe aufgeführt.  
  
|Wert|Ausgabe|  
|----------|-------------|  
|\+unendlich|`1.#INF` *random\-digits*|  
|\-unendlich|`–1.#INF` *random\-digits*|  
|unbestimmt \(mit stillem NaN identisch\)|*digit* `.#IND` *random\-digits*|  
|NAN|*digit* `.#NAN` *random\-digits*|  
  
> [!NOTE]
>  Wenn das `Buffer`\-Feld des Arguments, das `%Z` entspricht, oder des Arguments, das `%s` oder `%S` entspricht, ein NULL\-Zeiger ist, wird „\(NULL\)“ angezeigt.  
  
> [!NOTE]
>  In allen Exponentialformaten beträgt die Anzahl der Ziffern eines Exponenten, die angezeigt werden sollen, standardmäßig drei.  Mit der [\_set\_output\_format](../c-runtime-library/set-output-format.md)\-Funktion können Sie die Anzahl der angezeigten Ziffern, auf zwei festlegen und, falls aufgrund der Exponentengröße erforderlich, wieder auf drei Ziffern erweitern.  
  
> [!IMPORTANT]
>  Da das `%n`\-Format grundsätzlich unsicher ist, ist es standardmäßig deaktiviert.  Wenn `%n` in einer Formatzeichenfolge festgestellt wird, wird der ungültige Parameterhandler wie in [Parametervalidierung](../c-runtime-library/parameter-validation.md) beschrieben aufgerufen.  Informationen zum Aktivieren der `%n`\-Unterstützung finden Sie unter [\_set\_printf\_count\_output](../c-runtime-library/reference/set-printf-count-output.md).  
  
## Siehe auch  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Flag\-Direktiven](../c-runtime-library/flag-directives.md)   
 [printf\-Breitenangabe](../c-runtime-library/printf-width-specification.md)   
 [Genauigkeitsangabe](../c-runtime-library/precision-specification.md)   
 [Größenangabe](../c-runtime-library/size-specification.md)   
 [\_set\_output\_format](../c-runtime-library/set-output-format.md)