---
title: 'Vorgehensweise: Verwenden des Meldungszuordnungs-Querverweises | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fccdf620cbdaeffc7fb201e014edc4c7c1dddc83
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434452"
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

