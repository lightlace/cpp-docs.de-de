---
title: "Flag-Direktiven"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Flag-Direktiven für printf-Funktion"
  - "Formatangabefelder für printf-Funktion"
  - "Drucken von Flag-Direktiven"
  - "printf-Funktion, Formatangabefelder"
ms.assetid: b00cbdc9-1e5c-4b30-9f56-c1ef8d383767
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Flag-Direktiven
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einer Formatangabe ist das erste optionales Feld `flags`.  Flagdirektive sind ein Zeichen, das Ausgaberechtfertigung und Ausgabe von Zeichen, der Leerzeichen, von führenden Nullen von, Dezimaltrennzeichen und von oktalen und der hexadezimalen Präfixen angibt.  Mehr als eine Flagdirektive möglicherweise werden in einer Formatangabe, und Flags können in jeder Reihenfolge angezeigt werden.  
  
### Flag\-Zeichen  
  
|Flag|Bedeutung|Default|  
|----------|---------------|-------------|  
|`–`|Links ausrichten das Ergebnis innerhalb der angegebenen Feldbreite aus.|rechts stimmen überein.|  
|`+`|Verwenden Sie ein Zeichen \(\+ oder \-\) den Ausgabewert voranzustellen, wenn er ein Typ mit Vorzeichen liegt.|Zeichen wird nur für negative Werte mit Vorzeichen \(\-\).|  
|`0`|Wenn `width` Präfix `0` wird, werden führende Nullen hinzugefügt, bis die Mindestbreite erreicht ist.  Wenn `0` und `–` angezeigt werden, wird die `0` ignoriert.  Wenn `0` als ganze Format angegeben ist \(`i`, `u`, `x`, `X`, `o`, `d`\) und eine Genauigkeitsspezifikation ist auch Geschenk – z. B. wird `%04.d`\- `0` ignoriert.|Keine Auffüllung.|  
|Leerzeichen \(''\)|Verwenden Sie ein Leerzeichen, um den Ausgabewert voranzustellen, wenn er und Positiv signiert wird.  Der Zwischenraum wird ignoriert, wenn sowohl Leerzeichen und \+ Flags werden.|Kein Speicherplatz wird.|  
|`#`|Wenn es mit `o`, `x` oder `X` Format verwendet wurde, verwendet das `#`\-Flag 0 0x, 0X oder bzw. um beliebigen Wert ungleich 0 \(null\) s\-Ausgabewert voranzustellen.|Kein Speicherplatz wird.|  
||Wenn es mit `e`, `E`, `f`, `a` oder `A` Format verwendet wurde, wird das `#`\-Flag der Ausgabewert, um ein Dezimaltrennzeichen enthalten.|Dezimaltrennzeichen wird nur angezeigt, wenn Ziffern ihn befolgen.|  
||Wenn es mit `g` oder `G` Format verwendet wurde, verhindert die `#`\-Flagkräfte der Ausgabewert, ein Dezimaltrennzeichen enthalten und Clipping von nachfolgenden Nullen.<br /><br /> Wird ignoriert, wenn Sie mit `c`, `d`, `i`, `u` oder `s` verwendet werden.|Dezimaltrennzeichen wird nur angezeigt, wenn Ziffern ihn befolgen.  Nachfolgende Nullen werden abgeschnitten.|  
  
## Siehe auch  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [printf\-Breitenangabe](../c-runtime-library/printf-width-specification.md)   
 [Genauigkeitsangabe](../c-runtime-library/precision-specification.md)   
 [Größenangabe](../c-runtime-library/size-specification.md)   
 [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md)