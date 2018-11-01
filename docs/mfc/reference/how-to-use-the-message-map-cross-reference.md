---
title: 'Gewusst wie: Verwenden des Meldungszuordnungs-Querverweises'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.messages
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
ms.openlocfilehash: 71c46e7c30eab414534012c2fe314999568d2bd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457797"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Gewusst wie: Verwenden des Meldungszuordnungs-Querverweises

Einträge, die mit der Bezeichnung \<MemberFxn >, Schreiben Sie Ihre eigenen Member-Funktion für eine abgeleitete [CWnd](../../mfc/reference/cwnd-class.md) Klasse. Benennen Sie der Funktion alle gewünschten. Andere Funktionen wie `OnActivate`, werden die Memberfunktionen der Klasse `CWnd`. Wenn Sie aufgerufen wird, übergeben sie die Nachricht an die `DefWindowProc` Windows-Funktion. Um Windows-benachrichtigungsmeldungen zu verarbeiten, überschreiben Sie die entsprechenden `CWnd` -Funktion in der abgeleiteten Klasse. Ihre Funktion sollte die überschriebene Funktion in Ihrer Basisklasse können Sie die Basisklasse aufrufen, und Windows, die auf die Nachricht reagieren.

Fügen Sie in allen Fällen den Funktionsprototyp, in der `CWnd`-Header der abgeleiteten Klasse und Code Zuordnungseintrags Nachricht wie gezeigt.

Die folgenden Begriffe werden verwendet:

|Begriff|Definition|
|----------|----------------|
|ID|Alle benutzerdefinierten Menü-Element-ID (WM_COMMAND-Meldungen) oder die Steuerelement-ID (untergeordnete fenstermeldungen Benachrichtigung).|
|"Message" und "wNotifyCode schalten"|Windows message IDs an, wie in WINDOWS definiert. H.|
|nMessageVariable|Name einer Variablen, die den Rückgabewert enthält die `RegisterWindowMessage` Windows-Funktion.|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)

