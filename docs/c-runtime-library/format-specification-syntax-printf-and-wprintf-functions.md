---
title: "Syntax der Formatangabe: printf- und wprintf-Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Flag-Direktiven für printf-Funktion"
  - "Formatangabefelder für printf-Funktion"
  - "Präzisionsfelder"
  - "Drucken von Flag-Direktiven"
  - "printf-Funktion, Formatangabefelder"
  - "printf-Funktion, Präzision"
  - "type-Felder"
  - "type-Felder, printf-Funktion"
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Syntax der Formatangabe: printf- und wprintf-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt die Syntax für Argumente von Formatzeichenfolgen, die auf `printf`, `wprintf` und verwandte Funktionen verweisen.  Weitere sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter  [Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md).  Informationen zu den einzelnen Funktionen finden Sie in der Dokumentation zu den jeweiligen Funktionen.  Eine Auflistung dieser Funktionen finden Sie unter [Stream\-E\/A](../c-runtime-library/stream-i-o.md).  
  
 Eine Formatspezifikation, die aus optionalen Feldern und Pflichtfeldern besteht, hat die folgende Form:  
  
 `%`\[[flags](../c-runtime-library/flag-directives.md)\] \[[width](../c-runtime-library/printf-width-specification.md)\] \[**.**[precision](../c-runtime-library/precision-specification.md)\] \[{`h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`}\] [type](../c-runtime-library/printf-type-field-characters.md)  
  
 Jedes Feld der Formatspezifikation ist entweder ein Zeichen oder eine Zahl, das bzw. die eine bestimmte Formatoption oder Konvertierungsspezifizierer darstellt.  Das erforderliche `type`\-Zeichen gibt die Art der Konvertierung an, die an einem Argument vorgenommen wird.  Die optionalen Felder `flags`, `width` und die `precision` steuern zusätzliche Formataspekte.  Eine einfache Formatspezifikation enthält nur das Prozentzeichen und ein `type`\-Zeichen – z. B. `%s` für eine Zeichenfolgenkonvertierung.  In der sicheren Version der Funktionen wird ein ungültiger Parameterhandler aufgerufen, wenn einem Prozentzeichen ein Zeichen folgt, das keine Bedeutung für ein Formatfeld hat.  Weitere Informationen finden Sie unter [Parametervalidierung](../c-runtime-library/parameter-validation.md).  In den nicht sicheren Versionen wird das Zeichen unverändert in die Ausgabe kopiert.  Um ein Prozentzeichen zu drucken, verwenden Sie `%%`.  
  
 Die Felder der Formatspezifikation steuern die folgenden Aspekte der Argumentkonvertierung und Formatierung:  
  
 `type`  
 Erforderlicher Konvertierungsspezifizierer, der bestimmt, ob das dazugehörige `argument` als Zeichen, Zeichenfolge, ganze Zahl oder Gleitkommazahl interpretiert wird.  Weitere Informationen finden Sie unter [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md).  
  
 `flags`  
 Optionales Zeichen \(oder mehrere Zeichen\), das die Ausgaberechtfertigung und die Ausgabe von Zeichen, Leerzeichen, führenden Nullen, Dezimaltrennzeichen und von oktalen und hexadezimalen Präfixen steuert.  Weitere Informationen finden Sie unter [Flag\-Direktiven](../c-runtime-library/flag-directives.md).  In einer Formatspezifikation können mehrere Flags in beliebiger Reihenfolge angezeigt werden.  
  
 `width`  
 Optionaler Dezimalwert, der die Mindestanzahl von auszugebenden Zeichen angibt.  Weitere Informationen finden Sie unter [printf\-Breitenangabe](../c-runtime-library/printf-width-specification.md).  
  
 `precision`  
 Optionaler Dezimalwert, der die maximale Anzahl von den für Zeichenfolgen zu druckenden Zeichen angibt, die Anzahl der signifikanten Stellen oder die Anzahl von Ziffern nach dem Dezimaltrennzeichen für Gleitkommawerte, oder die Mindestanzahl an Ziffern, die für ganzzahlige Werte gedruckt werden.  Weitere Informationen finden Sie unter "Einfluss von Präzisionswerten auf den Typ" in [Genauigkeitsangabe](../c-runtime-library/precision-specification.md).  
  
 `h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`  
 Optionale Präfixe für `type`, die die Größe des entsprechenden Arguments angeben.  Weitere Informationen finden Sie unter "Größenpräfixe" in [Größenangabe](../c-runtime-library/size-specification.md).  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass die Formatspezifikationszeichenfolgen nicht benutzerdefiniert sind.  Beispiel: Ein Programm, das den Benutzer zur Eingabe eines Namens auffordert und die Eingabe in einer Zeichenfolgevariablen namens `name` speichert.  Führen Sie zum Drucken von `name` nicht diesen Schritt aus:  
>   
>  `printf( name ); /* Danger!  If name contains "%s", program will crash */`  
>   
>  Sondern gehen Sie stattdessen so vor:  
>   
>  `printf( "%s", name );`  
  
## Siehe auch  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf\_p\-Positionsparameter](../c-runtime-library/printf-p-positional-parameters.md)   
 [Flag\-Direktiven](../c-runtime-library/flag-directives.md)   
 [printf\-Breitenangabe](../c-runtime-library/printf-width-specification.md)   
 [Genauigkeitsangabe](../c-runtime-library/precision-specification.md)   
 [Größenangabe](../c-runtime-library/size-specification.md)   
 [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md)