---
title: "vprintf-Funktionen"
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
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "vprintf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Formatierter Text [C++]"
  - "vprintf-Funktion"
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# vprintf-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede der `vprintf`\-Funktionen verwendet einen Zeiger auf eine Argumentliste, anschließend zu Stilen und schreibt die angegebenen Daten einem bestimmten Ziel.  Die Funktionen unterscheiden sich in der ausgeführten Parametervalidierung, ob die Funktionen umfassend oder Einzelbyte\-Zeichenfolgen, das Ausgabeziel und die Unterstützung für das Angeben der Reihenfolge verwendet, bei der Parameter in der Formatzeichenfolge verwendet werden.  
  
|||  
|-|-|  
|[\_vcprintf, \_vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf\_s, \_vfprintf\_s\_l, vfwprintf\_s, \_vfwprintf\_s\_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|  
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[\_vprintf\_p, \_vprintf\_p\_l, \_vwprintf\_p, \_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|  
|[vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|  
|[\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|[vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|  
|[\_vscprintf, \_vscprintf\_l, \_vscwprintf, \_vscwprintf\_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[\_vsnprintf, \_vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|  
  
## Hinweise  
 Die `vprintf`\-Funktionen bei ihren Entsprechungsfunktionen ähnlich, wie in der folgenden Tabelle aufgeführt.  jedoch akzeptiert jede `vprintf`\-Funktion einen Zeiger auf eine Argumentliste, wenn jede der Entsprechungsfunktionen eine Argumentliste akzeptiert.  
  
 Diese Funktionen formatieren Daten für Ausgabe in Ziele wie folgt.  
  
|Funktion|Entsprechungsfunktion|Ausgabeziel|Parametervalidierung|Positionsgebundener Parameter\-Unterstützung|  
|--------------|---------------------------|-----------------|--------------------------|--------------------------------------------------|  
|`_vcprintf`|[\_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|Konsole|Überprüfung für NULL.|nein|  
|`_vcwprintf`|[\_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|Konsole|Überprüfung für NULL.|nein|  
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Stream*|Überprüfung für NULL.|nein|  
|**vfprintf\_p**|[fprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Stream*|Überprüfung für ungültig und gültiges Format.|ja|  
|`vfprintf_s`|[fprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Stream*|Überprüfung für ungültig und gültiges Format.|nein|  
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Stream*|Überprüfung für NULL.|nein|  
|**vfwprintf\_p**|[fwprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Stream*|Überprüfung für ungültig und gültiges Format.|ja|  
|`vfwprintf_s`|[fwprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Stream*|Überprüfung für ungültig und gültiges Format.|nein|  
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Überprüfung für NULL.|nein|  
|**vprintf\_p**|[printf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Überprüfung für ungültig und gültiges Format.|ja|  
|`vprintf_s`|[wie](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Überprüfung für ungültig und gültiges Format.|nein|  
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Überprüfung für NULL.|nein|  
|**vwprintf\_p**|[wprintf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Überprüfung für ungültig und gültiges Format.|ja|  
|`vwprintf_s`|[wprintf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Überprüfung für ungültig und gültiges Format.|nein|  
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für NULL.|nein|  
|**vsprintf\_p**|[sprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für ungültig und gültiges Format.|ja|  
|`vsprintf_s`|[sprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für ungültig und gültiges Format.|nein|  
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für NULL.|nein|  
|**vswprintf\_p**|[swprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für ungültig und gültiges Format.|ja|  
|`vswprintf_s`|[swprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für ungültig und gültiges Format.|nein|  
|`_vscprintf`|[\_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für NULL.|nein|  
|`_vscwprintf`|[\_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für NULL.|nein|  
|`_vsnprintf`|[\_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für NULL.|nein|  
|`_vsnwprintf`|[\_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|Speicher gezeigt auf durch *Puffer*|Überprüfung für NULL.|nein|  
  
 Das Argument `argptr` ist vom Typ `va_list`, der in VARARGS.H und in STDARG.H. definiert wird.  Die `argptr`\-Variable muss mit **va\_start,** initialisiert und wird durch folgenden Aufrufe `va_arg` initialisiert werden; `argptr` zeigt auf den Anfang einer Liste der Argumente, die für die Ausgabe entsprechend der entsprechenden Spezifikation im *Formatargument* konvertiert und gesendet werden.  *Format* hat die gleiche Form und Funktion wie das *Formatargument* für [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  Keine dieser Funktionsaufrufe `va_end`.  Eine ausführliche Beschreibung jeder `vprintf`\-Funktion, finden Sie in der Beschreibung der Entsprechungsfunktion, wie in der vorherigen Tabelle aufgeführt.  
  
 `_vsnprintf` unterscheidet sich von **vsprintf** dahingehend, dass nicht mehr als *Zählbytes* *dem Puffer* schreibt.  
  
 Die Versionen dieser Funktionen mit dem **w** Infix im Namen sind Breitzeichenversionen der entsprechenden Funktionen ohne das **w** Infix; in jedem dieser Breitzeichenfunktionen, sind *Puffer* und *Format* Zeichenfolgen mit Breitzeichen.  Andernfalls verhält sich jede Breitzeichenfunktion identisch mit der SBCS\-Entsprechungsfunktion.  
  
 Die Versionen dieser Funktionen mit **\_s** und **\_p** sind die Suffixe höhere Versionen.  Diese Versionen überprüfen die Formatzeichenfolgen und werden eine Ausnahme generieren, wenn der Formatzeichenfolge nicht regelkonform ist \(beispielsweise, wenn ungültige Formatierungszeichen verwendet werden\).  
  
 Die Versionen dieser Funktionen mit dem Suffix **\_p** bietet die Möglichkeit, die Reihenfolge anzugeben, in der die angegebenen Argumente in der Formatzeichenfolge ersetzt werden.  Weitere Informationen finden Sie unter [printf\_p\-Positionsparameter](../c-runtime-library/printf-p-positional-parameters.md).  
  
 Für **vsprintf**, `vswprintf`, `_vsnprintf` und `_vsnwprintf` wenn das Kopieren zwischen Zeichenfolgen erfolgt, die sich überschneiden, wird das Verhalten undefiniert.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass benutzerdefinierte *Format* keine Zeichenfolge ist.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  Wenn sie die sicheren Versionen dieser Funktionen \(entweder die **\_s** oder **\_p** Suffixe\), könnte eine vom Benutzer bereitgestellte Formatzeichenfolge eine ungültige Parameterausnahme auslösen, wenn die vom Benutzer bereitgestellte Zeichenfolge ungültige Formatierungszeichen enthält.  
  
## Siehe auch  
 [Stream\-E\/A](../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)