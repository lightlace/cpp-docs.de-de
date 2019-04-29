---
title: Klassen für die Ausgabe (Gerätekontext)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.output
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
ms.openlocfilehash: 1d76570e7bfd4ce587b3803235394ec5406d30b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410199"
---
# <a name="output-device-context-classes"></a>Klassen für die Ausgabe (Gerätekontext)

Diese Klassen kapseln die verschiedenen Typen von Gerätekontexten, die in Windows verfügbar.

Die meisten der folgenden Klassen kapseln ein Handle für einen Windows-Gerätekontext. Ein Gerätekontext ist ein Windows-Objekt, das Informationen über die Zeichnungsattribute eines Geräts z. B. einer Bildschirmanzeige oder einen Drucker enthält. Alle Zeichenbefehle erfolgen über ein Gerät-Context-Objekt. Zusätzliche Klassen abgeleitet `CDC` spezielle Gerätekontext-Funktionen, einschließlich der Unterstützung für Windows-Metadateien zu kapseln.

[CDC](../mfc/reference/cdc-class.md)<br/>
Die Basisklasse für Gerätekontexte. Direkt für den Zugriff auf die gesamte Anzeige und für den Zugriff auf Nondisplay-Kontexten wie z. B. Drucker verwendet.

[CPaintDC](../mfc/reference/cpaintdc-class.md)<br/>
Einen Anzeigekontext verwendet `OnPaint` Member-Funktionen von Windows. Ruft automatisch `BeginPaint` Erstellung und `EndPaint` bei Zerstörung.

[CClientDC](../mfc/reference/cclientdc-class.md)<br/>
Einen Anzeigekontext für Windows Client-Bereichen. Beispielsweise verwendet, um in eine sofortige Reaktion auf Mausereignisse zu zeichnen.

[CWindowDC](../mfc/reference/cwindowdc-class.md)<br/>
Einen Anzeigekontext für die gesamte Windows, einschließlich der Client und die nicht-Clientbereiche.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md)<br/>
Einen Gerätekontext für Windows-Metadateien. Eine Windows-Metadatei enthält eine Sequenz von Graphics Device Interface (GDI) Befehle, die wiedergegeben werden können, um ein Image zu erstellen. Die Memberfunktionen der Aufrufe einer `CMetaFileDC` in einer Metadatei aufgezeichnet werden.

## <a name="related-classes"></a>Verwandte Klassen

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Die Koordinate (X, y)-Paare enthält.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Enthält paarweise zugeordneten Werte, relativen Positionen oder Entfernung an.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Enthält die Koordinaten der rechteckige Bereiche.

[CRgn](../mfc/reference/crgn-class.md)<br/>
Kapselt einen GDI-Bereich zum Bearbeiten von einen elliptischen, unregelmäßige oder polygonalen Bereich innerhalb eines Zeitfensters an. In Verbindung mit den Clipping-Memberfunktionen in der Klasse verwendet `CDC`.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
Zeigt an, und die Benutzeroberfläche zum Ändern der Größe und verschieben die rechteckige Objekte behandelt.

[CColorDialog](../mfc/reference/ccolordialog-class.md)<br/>
Stellt ein Standarddialogfeld für die Auswahl einer Farbe bereit.

[CFontDialog](../mfc/reference/cfontdialog-class.md)<br/>
Stellt ein Standarddialogfeld für das Auswählen einer Schriftart an.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Stellt ein Standarddialogfeld zum Drucken einer Datei bereit.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
