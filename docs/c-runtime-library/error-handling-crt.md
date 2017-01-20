---
title: "Fehlerbehandlung (CRT)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "c.errors"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Fehlerbehandlung, Routinen in C für"
  - "Fehlerbehandlung, Bibliothekenroutinen"
  - "Logikfehler"
  - "Testen, für Programmfehler"
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Fehlerbehandlung (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese, um Programmfehler Routinen zu behandeln.  
  
### Fehlerbehandlungs\-Routinen  
  
|Routine|Verwendung|.NET Framework\-Entsprechung|  
|-------------|----------------|----------------------------------|  
|Makro [Assertion](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Test für Programmierlogikfehler; verfügbar in der Version und die Debugversionen der Laufzeitbibliothek|[\<caps:sentence id\="tgt8" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|Makros [\_ASSERT, \_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Wie auch `assert`, jedoch nur verfügbar in den Debugversionen der Laufzeitbibliothek|[\<caps:sentence id\="tgt11" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Rücksetzungsfehlerindikator.  Das Aufrufen von `rewind` oder das Schließen eines Streams kann außerdem den Fehler zurück.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_eof](../c-runtime-library/reference/eof.md)|Überprüfung Dateiende E\/A in der auf niedriger Ebene|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[feof](../c-runtime-library/reference/feof.md)|Test für Dateiende.  Dateiende wird auch wenn `_read`  gibt 0 angegeben.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[ferror](../c-runtime-library/reference/ferror.md)|Test für Stream E\/A\-Fehler|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|Makros [\_RPT, \_RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Generiert einen Bericht, der mit `printf` vergleichbar, jedoch die Debugversionen der Laufzeitbibliothek nur verfügbar ist|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_set\_error\_mode](../c-runtime-library/reference/set-error-mode.md)|Ändert das `__error_mode`, um einen nicht standardmäßigen Speicherort zu bestimmen, in dem die C\-Laufzeit eine Fehlermeldung für einen Fehler geschrieben wird, der möglicherweise das Programm beendet.||  
|[\_set\_purecall\_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Legt den Handler einer reinen virtuellen Funktionsaufruf fest.||  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)