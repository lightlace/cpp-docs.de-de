---
title: Druckvorschauarchitektur
ms.date: 11/04/2016
helpviewer_keywords:
- print preview [MFC], process
- previewing printing
- print preview [MFC], architecture
- printing [MFC], print preview
- print preview [MFC], modifications to MFC
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
ms.openlocfilehash: ea80b67b3f6bb6980e4e8f7f12a967cb7bb5b6c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218728"
---
# <a name="print-preview-architecture"></a>Druckvorschauarchitektur

In diesem Artikel wird erläutert, wie das MFC-Framework Seitenansichtsfunktionen implementiert. Zu den behandelten Themen gehören:

- [Seitenansicht-Prozess](#_core_the_print_preview_process)

- [Ändern der Seitenansicht](#_core_modifying_print_preview)

Seitenansicht liegt unterscheidet sich von der Bildschirmanzeige und den Druckvorgang, statt direkt ein Bild auf einem Gerät zu zeichnen, den Drucker mit dem Bildschirm die Anwendung simuliert werden muss. Um dies zu berücksichtigen, die Microsoft Foundation Class Library definiert eine spezielle (MFC)-Klasse, die von abgeleiteten [CDC-Klasse](../mfc/reference/cdc-class.md)namens `CPreviewDC`. Alle `CDC` Objekte enthalten zwei Gerätekontexte, aber sie sind in der Regel identisch. In einem `CPreviewDC` -Objekts können sie unterscheiden sich: der erste gibt den simulierten Drucker aus, und der zweite gibt den Bildschirm für die Ausgabe wird tatsächlich angezeigt.

##  <a name="_core_the_print_preview_process"></a> Vorgang der Seitenansicht

Wenn der Benutzer den Befehl "Seitenansicht" von auswählt der **Datei** Menü, das Framework erstellt eine `CPreviewDC` Objekt. Wenn Ihre Anwendung einen Vorgang, der ein Merkmal von den Druckergerätekontext festlegt ausführt, führt das Framework auch einen ähnlichen Vorgang auf dem Bildschirm Gerätekontext. Wenn Ihre Anwendung eine Schriftart für den Druck auswählt, wählt z. B. das Framework eine Schriftart für die Bildschirmanzeige, die die Druckerschriftart simuliert. Wenn Ihre Anwendung an den Drucker die Ausgabe senden möchten, sendet das Framework die Ausgabe stattdessen auf dem Bildschirm an.

Seitenansicht unterscheidet sich auch am drucken, in der Reihenfolge, die jeweils die Seiten eines Dokuments zeichnet. Während des Druckens, wird das Framework eine print, Loop fortgesetzt, bis auf ein bestimmten Bereich von Seiten gerendert wurde. Der Seitenansicht ein oder zwei Seiten zu einem beliebigen Zeitpunkt angezeigt werden, und klicken Sie dann die Anwendung wartet; keine weiteren Seiten werden angezeigt, bis der Benutzer reagiert. Der Seitenansicht muss die Anwendung auch auf WM_PAINT-Nachrichten reagieren, genau wie bei normalen Bildschirmanzeige.

Die [CView::OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) Funktion wird aufgerufen, wenn Sie den Vorschaumodus aufgerufen wird, ebenso wie zu Beginn eines Druckauftrags. Die [CPrintInfo-Struktur](../mfc/reference/cprintinfo-structure.md) an die Funktion übergebene Struktur enthält mehrere Elemente, deren Werte, die Sie festlegen können, um bestimmte Merkmale der Seitenansicht Operation anpassen. Sie können z. B. Festlegen der *M_nNumPreviewPages* Member angeben, ob Sie das Dokument im Modus "auf einer Seite oder zwei Seiten" Vorschau anzeigen möchten.

##  <a name="_core_modifying_print_preview"></a> Ändern der Seitenansicht

Sie können das Verhalten und die Darstellung der Seitenansicht in eine Reihe von Möglichkeiten recht einfache Weise ändern. Beispielsweise können Sie unter anderem:

- Dazu führen, dass der Seitenansicht, um eine Schiebeleiste für den leichteren Zugriff auf jeder Seite des Dokuments anzuzeigen.

- Führen Sie die Seitenansicht für Position im Dokument des Benutzers zu sorgen, indem Sie die Anzeige auf der aktuellen Seite ab.

- Führen Sie die verschiedenen Initialisierung für Seitenansicht und den Druckvorgang ausgeführt werden.

- Führen Sie die Seitenansicht zum Anzeigen von Seitenzahlen in Ihre eigenen Formate.

Wenn Sie wissen, wie lange das Dokument ist, und rufen Sie `SetMaxPage` mit den entsprechenden Wert ein, das Framework mithilfe dieser Informationen kann im Vorschaumodus sowie beim Drucken. Nachdem das Framework die Länge des Dokuments bekannt ist, können sie das Vorschaufenster eine Schiebeleiste, damit der Benutzer durch das Dokument im Vorschaumodus hin-und Seite bereitstellen. Wenn Sie die Länge des Dokuments festgelegt haben, kann nicht das Framework positionieren Sie das Bildlauffeld um die aktuelle Position anzugeben, damit das Framework eine Bildlaufleiste hinzugefügt wird. In diesem Fall muss die Benutzer die nächste Seite und vorherigen Seitenschaltflächen auf das Vorschaufenster Steuerleiste durch das Dokument verwenden.

Für die Seitenansicht, kann es hilfreich sein, einen Wert zuweisen der *M_nCurPage* Mitglied `CPrintInfo`, auch wenn Sie dies für den normalen Druck nie tun. Während der normalen Drucken enthält dieser Member der Informationen aus dem Framework in Ihrer Ansichtsklasse. Dies ist wie das Framework für die Ansicht mitteilt, welche Seite gedruckt werden soll.

Wenn hingegen die Seitenansicht-Modus gestartet wird, die *M_nCurPage* Element enthält die Informationen in die entgegengesetzte Richtung: aus der Ansicht für das Framework. Das Framework verwendet den Wert dieses Members, um zu bestimmen, welche Seite zuerst in der Vorschau angezeigt werden soll. Der Standardwert dieses Members ist 1, sodass zunächst die erste Seite des Dokuments angezeigt wird. Sie können außer Kraft setzen `OnPreparePrinting` , dieses Element auf der Anzahl der Seiten, die angezeigt wird, die zum Zeitpunkt der Befehl "Seitenansicht" aufgerufen wurde. Auf diese Weise verwendet die Anwendung aktuelle Position des Benutzers, beim Verschieben von aus normalen Anzeigemodus im Vorschaumodus zu drucken.

Manchmal möchten `OnPreparePrinting` zum Ausführen von anderen Initialisierung, je nachdem, ob sie für einen Druckauftrag oder für die Seitenansicht aufgerufen wird. Können Sie feststellen, durch Untersuchen der *M_bPreview* Membervariable in den `CPrintInfo` Struktur. Dieser Member nastaven NA hodnotu **"true"** Wenn Seitenansicht aufgerufen wird.

Die `CPrintInfo` Struktur enthält auch ein Element mit dem Namen *M_strPageDesc*, dient zum Formatieren der Zeichenfolgen, die am unteren Bildschirmrand in den Modi Einzelseiten- und mehrere Seiten angezeigt. Diese Zeichenfolgen sind standardmäßig im Format "Seite *n*" und "Seiten *n* - *m*," Sie können jedoch ändern *M_strPageDesc* aus in `OnPreparePrinting` , und legen Sie die Zeichenfolgen auf etwas Besseres einfallen. Finden Sie unter [CPrintInfo-Struktur](../mfc/reference/cprintinfo-structure.md) in die *MFC-Referenz* für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Drucken und Druckvorschau](../mfc/printing-and-print-preview.md)<br/>
[Drucken](../mfc/printing.md)<br/>
[CView-Klasse](../mfc/reference/cview-class.md)<br/>
[CDC-Klasse](../mfc/reference/cdc-class.md)
