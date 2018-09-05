---
title: 'Verstrichene Zeit: Automatisierungsklassen | Microsoft-Dokumentation'
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
ms.openlocfilehash: dcde08e8ffdb30f9ebf0ae7577bf836e84513a07
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751676"
---
# <a name="elapsed-time-automation-classes"></a>Verstrichene Zeit: Automatisierungsklassen

Dieses Verfahren wird gezeigt, wie zur Berechnung der Differenz zwischen zwei `CTime` Objekte an, und erhalten eine `CTimeSpan` Ergebnis.

#### <a name="to-calculate-elapsed-time"></a>Zum Berechnen der verstrichenen Zeit

1. Erstellen Sie zwei `COleDateTime` Objekte.

2. Legen Sie einen der `COleDateTime` Objekte auf die aktuelle Zeit.

3. Führen Sie eine zeitaufwändige Aufgabe.

4. Die andere `COleDateTime` Objekt, das die aktuelle Zeit.

5. Nehmen Sie den Unterschied zwischen den beiden Zeiten in Anspruch.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Datum und Uhrzeit: Automatisierungsunterstützung](../atl-mfc-shared/date-and-time-automation-support.md)

