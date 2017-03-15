---
title: Ausnahmebehandlungsroutinen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.exceptions
dev_langs:
- C++
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fe4946a8d3785c6295cb7537de0a11e06cd7a1cc
ms.lasthandoff: 02/24/2017

---
# <a name="exception-handling-routines"></a>Ausnahmebehandlungsroutinen
Verwenden Sie die C++-Ausnahmebehandlungsfunktionen, um nach unerwarteten Ereignissen während der Programmausführung eine Wiederherstellung durchzuführen.  
  
### <a name="exception-handling-functions"></a>Ausnahmebehandlungsfunktionen  
  
|Funktion|Verwendung|.NET Framework-Entsprechung|  
|--------------|---------|-------------------------------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Behandelt Win32-Ausnahmen (C-strukturierte Ausnahmen) als C++-typisierte Ausnahmen.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installiert Ihre eigene Beendigungsroutine, die von `terminate` aufgerufen werden soll.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installiert Ihre eigene Beendigungsfunktion, die von `unexpected` aufgerufen werden soll.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Wird nach dem Auslösen einer Ausnahme unter bestimmten Umständen automatisch aufgerufen. Die Funktion `terminate` ruft `abort` oder eine Funktion auf, die Sie mit `set_terminate` angeben.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Ruft `terminate` oder eine Funktion auf, die Sie mit `set_unexpected` angeben. Die Funktion `unexpected` wird in der aktuellen Microsoft C++-Ausnahmebehandlungsimplementierung nicht verwendet.|[System::Exception Class](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
