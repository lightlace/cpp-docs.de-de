---
title: 'Verstrichene Zeit: Allzweckklassen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating
- elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51eea60669fb7ad35525d65013ffc8420649349b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="elapsed-time-general-purpose-classes"></a>Verstrichene Zeit: Allgemeine Klassen
Das folgende Verfahren zeigt, wie zur Berechnung der Differenz zwischen zwei `CTime` Objekte und Abrufen einer `CTimeSpan` Ergebnis.  
  
#### <a name="to-calculate-elapsed-time"></a>Zum Berechnen der verstrichenen Zeit  
  
1.  Verwenden der `CTime` und `CTimeSpan` -Objekten, die verstrichene Zeit folgendermaßen berechnen:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]  
  
     Sobald Sie berechnet haben `elapsedTime`, können Sie die Memberfunktionen von `CTimeSpan` , die die verstrichene Zeit-Wert zu extrahieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit: Allgemeine Klassen](../atl-mfc-shared/date-and-time-general-purpose-classes.md)

