---
title: 'Verstrichene Zeit: Automatisierungsklassen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating in Automation
- Automation classes, elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1abf6274137ae67b159ad43612d24020a0d14e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="elapsed-time-automation-classes"></a>Verstrichene Zeit: Automatisierungsklassen
Dieses Verfahren wird gezeigt, wie zur Berechnung der Differenz zwischen zwei `CTime` Objekte und Abrufen einer `CTimeSpan` Ergebnis.  
  
#### <a name="to-calculate-elapsed-time"></a>Zum Berechnen der verstrichenen Zeit  
  
1.  Erstellen Sie zwei `COleDateTime` Objekte.  
  
2.  Legen Sie eine von der `COleDateTime` Objekte auf die aktuelle Uhrzeit.  
  
3.  Führen Sie einige zeitaufwändig.  
  
4.  Die andere `COleDateTime` Objekt, das die aktuelle Uhrzeit.  
  
5.  Nehmen Sie den Unterschied zwischen den zwei Mal in Anspruch.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit: Automatisierungsunterstützung](../atl-mfc-shared/date-and-time-automation-support.md)

