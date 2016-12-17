---
title: "Ausnahmebehandlungsroutinen"
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
  - "c.exceptions"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Ausnahmebehandlung, Routinen"
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Ausnahmebehandlungsroutinen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie die C\+\+\-Ausnahmebehandlungsfunktionen, um von unerwarteten Ereignissen während der Programmausführung zu beheben.  
  
### Ausnahmebehandlungs\-Funktionen  
  
|Funktion|Verwendung|.NET Framework\-Entsprechung|  
|--------------|----------------|----------------------------------|  
|[\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)|Behandeln Sie Win32\-Ausnahmen \(C\-strukturierte Ausnahmen\) als C\+\+ eingab Ausnahmen|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[set\_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installieren Sie eine eigene Methode von `terminate` aufgerufen werden Enderoutine,|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installieren Sie eine eigene Methode von `unexpected` aufgerufen werden Beendigungsfunktion,|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Wird automatisch aufgerufen wird unter bestimmten Umständen nach Ausnahme ausgelöst.  Die `terminate` durch `abort` oder Funktion, die Sie mit `set_terminate` angeben|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Aufrufe `terminate` oder Funktion, die Sie mit `set_unexpected` angeben.  Die `unexpected`\-Funktion wird nicht in der aktuellen C\+\+\-Ausnahmebehandlungsimplementierung Microsoft verwendet|[\<caps:sentence id\="tgt30" sentenceid\="ec8332f3bf55c7bd183338eca87744ec" class\="tgtSentence"\>System::Exception\-Klasse\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)