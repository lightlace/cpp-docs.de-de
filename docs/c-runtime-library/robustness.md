---
title: "Stabilität | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.runtime
dev_langs: C++
helpviewer_keywords: robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 27412403fe6ce0f1884a2ea99790376acb1c5236
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="robustness"></a>Stabilität
Verwenden Sie die folgenden C-Laufzeitbibliotheksfunktionen, um die Stabilität des Programms zu verbessern.  
  
### <a name="run-time-robustness-functions"></a>Funktionen für die Laufzeitstabilität  
  
|Funktion|Verwendung|  
|--------------|---------|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Übergibt die Steuerung an den Fehlerbehandlungsmechanismus, wenn der `new`-Operator keine Speicherbelegung vornehmen kann.|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Behandelt Win32-Ausnahmen (C-strukturierte Ausnahmen) als C++-typisierte Ausnahmen.|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installiert Ihre eigene Beendigungsfunktion, die von [terminate](../c-runtime-library/reference/terminate-crt.md) aufgerufen werden soll.|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installiert Ihre eigene Beendigungsfunktion, die von [unexpected](../c-runtime-library/reference/unexpected-crt.md) aufgerufen werden soll.|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)