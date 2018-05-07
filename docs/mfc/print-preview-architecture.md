---
title: Druckvorschauarchitektur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- print preview [MFC], process
- previewing printing
- print preview [MFC], architecture
- printing [MFC], print preview
- print preview [MFC], modifications to MFC
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26771ba3f5a79716a759327f485a92391fada8c7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="print-preview-architecture"></a>Druckvorschauarchitektur
In diesem Artikel wird erläutert, wie die MFC-Grundstruktur Seitenansichtsfunktionen implementiert. Zu den behandelten Themen gehören:  
  
-   [Seitenansicht-Prozess](#_core_the_print_preview_process)  
  
-   [Ändern der Seitenansicht](#_core_modifying_print_preview)  
  
 Seitenansicht ist unterscheidet sich von der Bildschirmanzeige und den Druckvorgang, da statt direkt ein Bild auf einem Gerät zu zeichnen, den Drucker mit dem Bildschirm als Herkunftszone der Anwendung muss. Um dies zu berücksichtigen, die Microsoft Foundation Class Library definiert eine spezielle (nicht dokumentierte)-Klasse, die abgeleitet [CDC-Klasse](../mfc/reference/cdc-class.md)namens **CPreviewDC**. Alle `CDC` Objekte enthalten zwei Gerätekontexte, aber in der Regel sind identisch. In einer **CPreviewDC** -Objekt, diese verschieden sind: der erste gibt den Drucker simuliert wird, und der zweite gibt den Bildschirm, auf dem tatsächlich Ausgabe angezeigt wird.  
  
##  <a name="_core_the_print_preview_process"></a> Der Prozess der Seitenansicht  
 Wenn der Benutzer wählt den Befehl "Seitenansicht" aus der **Datei** Menü, erstellt das Framework eine **CPreviewDC** Objekt. Wenn Ihre Anwendung einen Vorgang, der ein Merkmal von den Druckergerätekontext festlegt ausführt, führt das Framework auch einen ähnlichen Vorgang auf dem Bildschirm Gerätekontext. Wenn Ihre Anwendung eine Schriftart für den Druck auswählt, wählt z. B. das Framework eine Schriftart für die Bildschirmanzeige, das die Druckerschriftart simuliert. Wenn Ihre Anwendung die Ausgabe an den Drucker senden würde, sendet das Framework stattdessen die Ausgabe auf dem Bildschirm.  
  
 Seitenansicht unterscheidet sich auch am drucken, in der Reihenfolge der einzelnen Seiten eines Dokuments zeichnet. Während des Druckens weiterhin das Framework eine drucken-Schleife, bis auf ein bestimmten Bereich von Seiten gerendert wurde. Während der Seitenansicht zu blättern werden ein oder zwei Seiten zu einem beliebigen Zeitpunkt angezeigt, und klicken Sie dann die Anwendung wartet; keine weiteren Seiten werden angezeigt, bis der Benutzer reagiert. Während der Seitenansicht zu blättern, muss die Anwendung auch auf reagieren `WM_PAINT` Nachrichten verwenden, so wie er während der normalen Bildschirmanzeige ist.  
  
 Die [CView::OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) Funktion wird aufgerufen, wenn im Vorschaumodus aufgerufen wird, so wie dies am Anfang eines Druckauftrags erfolgt. Die [CPrintInfo-Struktur](../mfc/reference/cprintinfo-structure.md) an die Funktion übergebene Struktur enthält mehrere Elemente, deren Werte, die Sie festlegen können, um bestimmte Merkmale des Seitenansichtsvorgangs anpassen. Sie können z. B. Festlegen der **M_nNumPreviewPages** Member, um anzugeben, ob Sie das Dokument im einseitigen oder zweiseitigen Modus in der Vorschau anzeigen möchten.  
  
##  <a name="_core_modifying_print_preview"></a> Ändern der Seitenansicht  
 Sie können das Verhalten und die Darstellung der Seitenansicht auf vielfältige Weise leicht ändern. Beispielsweise können Sie, unter anderem:  
  
-   Führen Sie die Druckvorschaufenster eine Bildlaufleiste, um einen problemlosen Zugriff auf einer beliebigen Seite des Dokuments angezeigt.  
  
-   Führen Sie die Seitenansicht an Position im Dokument des Benutzers zu verwalten, indem Sie seine Anzeige auf die aktuelle Seite ab.  
  
-   Führen Sie verschiedene Initialisierung für Seitenansicht und den Druckvorgang ausgeführt werden.  
  
-   Führen Sie die Seitenansicht zum Anzeigen von Seitenzahlen in Ihren eigenen Formaten.  
  
 Wenn Sie wissen, wie lange das Dokument ist, und rufen Sie `SetMaxPage` mit den entsprechenden Wert der Framework mithilfe dieser Informationen kann im Vorschaumodus sowie während des Druckens. Nachdem das Framework die Länge des Dokuments bekannt ist, können sie im Vorschaufenster eine Bildlaufleiste, sodass der Benutzer das Dokument im Vorschaumodus hin-und durchblättern bereitstellen. Wenn Sie die Länge des Dokuments festgelegt haben, kann nicht das Framework das Bildlauffeld durch, um die aktuelle Position anzugeben, damit das Framework eine Bildlaufleiste hinzufügen nicht positionieren. In diesem Fall muss der Benutzer die nächste Seite und die vorherige Seite Schaltflächen auf der Seite durch das Dokument im Vorschaufenster Steuerleiste verwenden.  
  
 Für die Seitenansicht, Sie finden es vielleicht hilfreich, einen Wert zuweisen der `m_nCurPage` Mitglied `CPrintInfo`, obwohl Sie nie für den normalen Druck tun würden. Während des normalen Druckens führt bei diesem Member Informationen aus dem Framework in Ihrer Ansichtsklasse. Dies ist wie das Framework für die Sicht mitteilt, welche Seite gedruckt werden soll.  
  
 Wenn dagegen Seitenansicht gestartet ist, die `m_nCurPage` Member, der Informationen in die entgegengesetzte Richtung überträgt: aus der Sicht, um das Framework. Das Framework verwendet den Wert dieses Elements, um zu bestimmen, welche Seite zuerst in der Vorschau angezeigt werden soll. Der Standardwert dieses Elements ist 1, damit die erste Seite des Dokuments anfänglich angezeigt wird. Sie können außer Kraft setzen `OnPreparePrinting` festzulegende dieses Elements auf die Anzahl der Seite angezeigt wird, die zum Zeitpunkt der Befehl "Seitenansicht" aufgerufen wurde. Auf diese Weise verwaltet die Anwendung aktuelle Position des Benutzers, beim Verschieben von normalen Anzeigemodus, um die Seitenansicht.  
  
 Manchmal möchten `OnPreparePrinting` zum Ausführen von anderen Initialisierung abhängig davon, ob sie für einen Druckauftrag oder für die Seitenansicht aufgerufen wird. Sie können dies durch Untersuchen Ermitteln der **M_bPreview** Membervariable in der `CPrintInfo` Struktur. Bei diesem Member wird festgelegt, um **"true"** Wenn Seitenansicht aufgerufen wird.  
  
 Die `CPrintInfo` Struktur enthält auch ein Element mit dem Namen **M_strPageDesc**, der verwendet wird, formatieren Sie die Zeichenfolgen, die am unteren Rand des Bildschirms in den Modi Einzelseiten und mehreren Seiten angezeigt. Standardmäßig sind diese Zeichenfolgen im Format "Seite *n*" und "Seiten *n* - *m*,", aber Sie können ändern, **M_strPageDesc** aus in `OnPreparePrinting` , und legen Sie die Zeichenfolgen auf etwas komplexeren. Finden Sie unter [CPrintInfo-Struktur](../mfc/reference/cprintinfo-structure.md) in der *MFC-Referenz* für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Drucken und Druckvorschau](../mfc/printing-and-print-preview.md)   
 [Drucken](../mfc/printing.md)   
 [CView-Klasse](../mfc/reference/cview-class.md)   
 [CDC-Klasse](../mfc/reference/cdc-class.md)
