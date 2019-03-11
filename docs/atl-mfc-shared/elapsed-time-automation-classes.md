---
title: 'Verstrichene Zeit: Automatisierungsklassen'
ms.date: 11/04/2016
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
ms.openlocfilehash: d6a77d57a88166354fcb222c0da09690426108e9
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750048"
---
# <a name="elapsed-time-automation-classes"></a>Verstrichene Zeit: Automatisierungsklassen

Dieses Verfahren wird gezeigt, wie zur Berechnung der Differenz zwischen zwei `CTime` Objekte an, und erhalten eine `CTimeSpan` Ergebnis.

## <a name="to-calculate-elapsed-time"></a>Zum Berechnen der verstrichenen Zeit

1. Erstellen Sie zwei `COleDateTime` Objekte.

1. Legen Sie einen der `COleDateTime` Objekte auf die aktuelle Zeit.

1. Führen Sie eine zeitaufwändige Aufgabe.

1. Die andere `COleDateTime` Objekt, das die aktuelle Zeit.

1. Nehmen Sie den Unterschied zwischen den beiden Zeiten in Anspruch.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Datum und Uhrzeit: Automatisierungsunterstützung](../atl-mfc-shared/date-and-time-automation-support.md)
