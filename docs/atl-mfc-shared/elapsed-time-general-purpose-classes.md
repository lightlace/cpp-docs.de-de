---
title: 'Verstrichene Zeit: Allgemeine Klassen'
ms.date: 11/04/2016
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
ms.openlocfilehash: 5990f6f5db0270c8d24ff35b5c9bbea5b24e6ed7
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742040"
---
# <a name="elapsed-time-general-purpose-classes"></a>Verstrichene Zeit: Allgemeine Klassen

Das folgende Verfahren zeigt, wie zur Berechnung der Differenz zwischen zwei `CTime` Objekte an, und erhalten eine `CTimeSpan` Ergebnis. Verwenden der `CTime` und `CTimeSpan` Objekte, die verstrichene Zeit folgendermaßen berechnen:

   [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]

Nachdem Sie berechnet haben `elapsedTime`, können Sie die Memberfunktionen der `CTimeSpan` die Bestandteile der verstrichene Zeit-Wert zu extrahieren.
