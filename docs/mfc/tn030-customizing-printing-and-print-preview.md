---
title: 'TN030: Anpassen des Druckvorgangs und der Seitenansicht | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.print
dev_langs:
- C++
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8331bbde9cf749d3b86b8970543d7a3b46be90fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381139"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030: Anpassen des Druckvorgangs und der Druckvorschau

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis beschreibt den Prozess, Drucken und Druckvorschau und im Rahmen der Rückruf-Routinen in verwendet `CView` und die Rückruf-Routinen und Memberfunktionen der `CPreviewView`.

## <a name="the-problem"></a>Das Problem

MFC bietet eine umfassende Lösung für die meisten drucken und Druckvorschau benötigt. In den meisten Fällen ist ein wenig zusätzlicher Code erforderlich, um eine Ansicht Vorschau und drucken können. Aber es gibt Möglichkeiten, Drucken zu optimieren, die erfordern erheblichen Aufwand seitens des Entwicklers, und einige Anwendungen müssen bestimmte Elemente der Benutzeroberfläche in den Seitenansicht-Modus hinzufügen.

## <a name="efficient-printing"></a>Effiziente drucken

Wenn eine MFC-Anwendung gedruckt wird, verwenden die Standardmethoden, leitet Windows alle Graphical Device Interface (GDI) Ausgabe-Aufrufe an eine in-Memory-Metadatei an. Wenn `EndPage` wird aufgerufen, spielt Windows die Metadatei einmal für jedes physische Band, das der Drucker erfordert, um eine Seite zu drucken. Während dieses Rendering fragt GDI häufig die Abbrechen-Prozedur, um zu bestimmen, ob er fortgesetzt werden soll. In der Regel ermöglicht die Abort-Prozedur Nachrichten verarbeitet werden, damit der Benutzer den Druckauftrag, über ein Dialogfeld "Drucken" Abbrechen kann.

Leider kann dies den Druckvorgang verlangsamen. Wenn das Drucken in Ihrer Anwendung schneller, als Sie mithilfe der standardmäßigen Technik erreicht werden kann sein muss, müssen Sie die manuelle banding implementieren.

## <a name="print-banding"></a>Drucken Sie die Bereiche

Um manuell--Band-, müssen Sie erneut implementieren die print-Schleife so, dass `OnPrint` mehrmals pro Seite (je einmal pro Band) aufgerufen wird. Die print-Schleife wird implementiert, der `OnFilePrint` -Funktion in viewprnt.cpp. In Ihrer `CView`-abgeleitete Klasse sein, Sie diese Funktion überladen, sodass der Eintrag für die Zuordnung von Nachrichten für die Behandlung des Druckbefehl die print-Funktion aufruft. Kopieren der `OnFilePrint` Routine und ändern Sie den print, Loop um Bereiche zu implementieren. Wahrscheinlich werden Sie möchten auch das Bereichsmethoden Rechteck an Ihre Drucken Funktionen übergeben, sodass Sie basierend auf den Abschnitt der zu druckenden Seite zeichnen optimieren können.

Zweitens müssen Sie häufig aufrufen `QueryAbort` beim Zeichnen des Bands. Andernfalls die Abbrechen-Prozedur nicht aufgerufen, und der Benutzer wird in der Lage, den Druckauftrag abbrechen.

## <a name="print-preview-electronic-paper-with-user-interface"></a>Seitenansicht: Elektronisches Dokument mit Benutzeroberfläche

Seitenansicht, versucht im Wesentlichen um die Anzeige in eine Emulation von einem Drucker zu aktivieren. Standardmäßig dient das den Clientbereich des Hauptfensters ein oder zwei Seiten vollständig innerhalb des Fensters angezeigt. Der Benutzer kann zum Vergrößern auf einen Bereich der Seite, um weitere Details zu erkennen. Mit zusätzlicher Unterstützung wird der Benutzer auch so bearbeiten Sie das Dokument in der Vorschau zugelassen.

## <a name="customizing-print-preview"></a>Anpassen der Seitenansicht

In diesem Hinweis befasst sich nur mit einem Aspekt des Ändern der Seitenansicht: Hinzufügen von Benutzeroberflächen in den Vorschaumodus. Andere Änderungen sind möglich, aber diese Änderungen sind nicht Gegenstand dieser Diskussion.

## <a name="to-add-ui-to-the-preview-mode"></a>Der Vorschaumodus Benutzeroberfläche hinzu

1. Leiten Sie eine Klasse anzeigen von `CPreviewView`.

2. Fügen Sie Befehlshandler für das die UI-Aspekte, die Sie wünschen.

3. Wenn Sie visuelle Aspekte der Anzeige hinzufügen, überschreiben `OnDraw` und führen Sie die Zeichnung nach dem Aufruf `CPreviewView::OnDraw`.

## <a name="onfileprintpreview"></a>OnFilePrintPreview

Dies ist der Befehlshandler für die Seitenansicht. Die Standardimplementierung ist:

```cpp
void CView::OnFilePrintPreview()
{
    // In derived classes, implement special window handling here
    // Be sure to Unhook Frame Window close if hooked.

    // must not create this on the frame. Must outlive this function
    CPrintPreviewState* pState = new CPrintPreviewState;

    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR, this,
        RUNTIME_CLASS(CPreviewView), pState))
    {
        // In derived classes, reverse special window handling
        // here for Preview failure case

        TRACE0("Error: DoPrintPreview failed");
        AfxMessageBox(AFX_IDP_COMMAND_FAILURE);
        delete pState;  // preview failed to initialize, delete State now
    }
}
```

`DoPrintPreview` im Hauptfenster der Anwendung wird ausgeblendet werden. Steuerleisten, z. B. der Statusleiste können beibehalten werden durch deren Angabe in der pState ->*DwStates* Member (Dies ist eine Bitmaske und die Bits für einzelne Steuerleisten von AFX_CONTROLBAR_MASK (AFX_IDW_MYBAR) definiert sind). Das Fenster pState ->*nIDMainPane* wird das Fenster, das automatisch reshown und ausgeblendet werden soll. `DoPrintPreview` wird eine Schaltflächenleiste wird dann für die Preview-Benutzeroberfläche erstellt werden. Wenn besondere Fensters Verarbeitung erforderlich ist, z. B. aus- oder Einblenden von anderen Fenstern, die vor dem erfolgen soll `DoPrintPreview` aufgerufen wird.

Standardmäßig bei der Seitenansicht abgeschlossen ist, wird zurückgegeben die Steuerleisten auf den ursprünglichen Zustand und im Hauptfenster zu sichtbar. Wenn besondere Behandlung erforderlich ist, dieser Vorgang sollte in einer Außerkraftsetzung der `EndPrintPreview`. Wenn `DoPrintPreview` ein Fehler auftritt, bieten auch spezielle Behandlung.

DoPrintPreview ist mit dem Namen:

- Die Ressourcen-ID der Dialogfeldvorlage für die vorschausymbolleiste.

- Ein Zeiger auf die Ansicht, um den Druckvorgang für die Seitenansicht ausführen.

- Die Laufzeit-Klasse der Vorschauansicht-Klasse. Dies wird im DoPrintPreview dynamisch erstellt werden.

- Der Zeiger CPrintPreviewState. Beachten Sie, dass die CPrintPreviewState-Struktur (oder die abgeleiteten-Struktur, wenn die Anwendung weitere Zustands benötigt) muss *nicht* im Frame erstellt werden. DoPrintPreview ist ohne Modus aus, und diese Struktur muss überstehen, bis EndPrintPreview aufgerufen wird.

  > [!NOTE]
  > Wenn eine separate Ansicht oder die View-Klasse für die druckunterstützung erforderlich ist, sollte ein Zeiger auf das Objekt als der zweite Parameter übergeben werden.

## <a name="endprintpreview"></a>EndPrintPreview

Dies wird aufgerufen, um den Seitenansichtmodus zu beenden. Es ist häufig wünschenswert, wechseln zur Seite im Dokument, die zuletzt in der Seitenansicht angezeigt wurde. `EndPrintPreview` ist die Anwendung Gelegenheit dazu. Die "pInfo" ->*M_nCurPage* Member ist die Seite, die zuletzt (am weitesten links angezeigt wurden, wenn zwei Seiten angezeigt wurden, ist), und der Zeiger ist ein Hinweis auf, in dem auf der Seite der Benutzer daran interessiert waren. Da die Struktur der Sicht von der Anwendung das Framework nicht bekannt ist, müssen Sie den Code zum Verschieben auf den ausgewählten Zeitpunkt angeben.

Sie sollten die meisten Aktionen vor dem Aufruf `CView::EndPrintPreview`. Dieser Aufruf kehrt die Auswirkungen der `DoPrintPreview` und löscht pView, pDC und "pInfo".

```cpp
// Any further cleanup should be done here.
CView::EndPrintPreview(pDC, pInfo, point, pView);
```

## <a name="cwinapponfileprintsetup"></a>CWinApp::OnFilePrintSetup

Dies muss für das Menüelement für Print Setup zugeordnet werden. In den meisten Fällen ist es nicht erforderlich, die Implementierung zu überschreiben.

## <a name="page-nomenclature"></a>Seite-Terminologie

Ein weiteres Problem ist, die der Seitennummerierung und Reihenfolge. Für einfache Textverarbeitungsprogramm Typ Anwendungen ist dies ein Problem einfach. Die meisten Systeme für die Seitenansicht wird davon ausgegangen, dass eine Seite im Dokument jede gedruckte Seite entspricht.

In den Versuch, eine allgemeine Lösung bereitstellen, sind einige Punkte zu berücksichtigen. Angenommen Sie, ein CAD-System. Der Benutzer hat eine Zeichnung, die mehrere E-Format Tabellen abdeckt. Eine E-Größe (oder eine kleinere, skaliert) Plotter, Seitennummerierung wie im einfachen Fall wäre. Aber auf einem Laserdrucker, Drucken von 16 ein Größe Seiten pro Seite, was die Seitenansicht berücksichtigt "Seite"

Wie in der einführenden Abschnitt angegeben, fungiert wie ein Drucker Seitenansicht. Aus diesem Grund wird dem Benutzer angezeigt, was aus der bestimmten Drucker werden würde, das ausgewählt ist. Es ist Aufgabe der Ansicht, um zu bestimmen, welches Bild auf jeder Seite gedruckt wird.

Die Seite "Description-Zeichenfolge in die `CPrintInfo` Struktur bietet eine Möglichkeit zum Anzeigen von der Seitenzahl für den Benutzer, wenn es als eine Zahl pro Seite dargestellt werden kann (wie in der"Seite 1"oder" Seiten 1 – 2"). Diese Zeichenfolge wird verwendet, indem Sie die standardmäßige Implementierung des `CPreviewView::OnDisplayPageNumber`. Wenn Sie ein anderen Bildschirm erforderlich ist, kann eine dieser virtuelle Funktion, z. B. "Tabelle1, Abschnitte A, B" Bereitstellen überschreiben.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
