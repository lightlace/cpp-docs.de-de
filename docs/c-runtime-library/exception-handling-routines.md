---
title: Ausnahmebehandlungsroutinen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.exceptions
dev_langs: C++
helpviewer_keywords: exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d12410aba4f64f54cbbfcc123d842171441192a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="exception-handling-routines"></a>Ausnahmebehandlungsroutinen
Verwenden Sie die C++-Ausnahmebehandlungsfunktionen, um nach unerwarteten Ereignissen während der Programmausführung eine Wiederherstellung durchzuführen.  
  
### <a name="exception-handling-functions"></a>Ausnahmebehandlungsfunktionen  
  
|Funktion|Verwendung|  
|--------------|---------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Behandelt Win32-Ausnahmen (C-strukturierte Ausnahmen) als C++-typisierte Ausnahmen.|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installiert Ihre eigene Beendigungsroutine, die von `terminate` aufgerufen werden soll.|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installiert Ihre eigene Beendigungsfunktion, die von `unexpected` aufgerufen werden soll.|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Wird nach dem Auslösen einer Ausnahme unter bestimmten Umständen automatisch aufgerufen. Die Funktion `terminate` ruft `abort` oder eine Funktion auf, die Sie mit `set_terminate` angeben.|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Ruft `terminate` oder eine Funktion auf, die Sie mit `set_unexpected` angeben. Die Funktion `unexpected` wird in der aktuellen Microsoft C++-Ausnahmebehandlungsimplementierung nicht verwendet.|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)