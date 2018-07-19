---
title: 'Verstrichene Zeit: Allzweckklassen | Microsoft Docs'
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
- elapsed time, calculating
- elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff7ef11bb20124a05e2e85c408ce27de8f982546
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354265"
---
# <a name="elapsed-time-general-purpose-classes"></a>Verstrichene Zeit: Allgemeine Klassen
Das folgende Verfahren zeigt, wie zur Berechnung der Differenz zwischen zwei `CTime` Objekte und Abrufen einer `CTimeSpan` Ergebnis.  
  
#### <a name="to-calculate-elapsed-time"></a>Zum Berechnen der verstrichenen Zeit  
  
1.  Verwenden der `CTime` und `CTimeSpan` -Objekten, die verstrichene Zeit folgendermaßen berechnen:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]  
  
     Sobald Sie berechnet haben `elapsedTime`, können Sie die Memberfunktionen von `CTimeSpan` , die die verstrichene Zeit-Wert zu extrahieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit: Allgemeine Klassen](../atl-mfc-shared/date-and-time-general-purpose-classes.md)

