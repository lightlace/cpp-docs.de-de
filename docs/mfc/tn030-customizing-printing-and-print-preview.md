---
title: 'TN030: Anpassen des Druckvorgangs und der Druckvorschau | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 342edd56ee279de0b854c8e8ceb177b797a03f3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384610"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030: Anpassen des Druckvorgangs und der Druckvorschau
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt den Prozess der drucken und Druckvorschau anpassen und im Rahmen der Rückruf-Routinen in verwendet `CView` und die Rückruf-Routinen und Memberfunktionen der **CPreviewView**.  
  
## <a name="the-problem"></a>Das Problem  
 MFC bietet eine umfassende Lösung für die meisten drucken und Druckvorschau benötigt. In den meisten Fällen ist nur wenig zusätzlicher Code erforderlich, um eine Ansicht zu drucken und in der Vorschau anzeigen können. Allerdings stehen Möglichkeiten zur Optimierung der drucken, die erheblichen Aufwand seitens des Entwicklers erforderlich ist, und einige Anwendungen müssen bestimmte Elemente der Benutzeroberfläche der Seitenansicht hinzufügen.  
  
## <a name="efficient-printing"></a>Effiziente drucken  
 Wenn eine MFC-Anwendung die Standardmethoden verwenden druckt, leitet Windows alle Graphical Device Interface (GDI) Ausgabe-Aufrufe an eine in-Memory-Metadatei an. Wenn `EndPage` wird aufgerufen, spielt Windows die Metadatei einmal für jedes physische Band, das der Drucker ist erforderlich, um eine Seite zu drucken. Während dieses Rendering abgefragt GDI häufig die Prozedur abbrechen, um zu bestimmen, ob er fortgesetzt werden soll. In der Regel ermöglicht das Abbruchvorgangs Nachrichten verarbeitet werden, damit der Benutzer den Druckauftrag mit einem Dialogfeld "Drucken" abgebrochen wird.  
  
 Leider kann dies den Druckvorgang verlangsamt werden. Wenn das Drucken in Ihrer Anwendung schneller als die Verwendung der Standardmethode erreicht werden kann sein muss, müssen Sie die manuelle banding implementieren.  
  
## <a name="print-banding"></a>Banding drucken  
 Um manuell band, müssen Sie erneut implementieren die Druckschleife so, dass `OnPrint` mehrmals pro Seite (einmal pro Band) aufgerufen. Drucken-Schleife wird implementiert, der **OnFilePrint** -Funktion in viewprnt.cpp. In Ihrem `CView`-abgeleitete Klasse, Sie diese Funktion überladen, sodass Zuordnungseintrags Nachricht für die Behandlung der Druckbefehl print-Funktion aufruft. Kopieren der **OnFilePrint** Routine und ändern die Druckschleife banding implementieren. Möglicherweise möchten Sie auch das Bereichsmethoden Rechteck zum Drucken Funktionen übergeben, sodass Zeichnung basierend auf den Abschnitt der Seite gedruckt wird optimiert werden kann.  
  
 Zweitens müssen Sie häufig aufrufen `QueryAbort` beim Zeichnen des Bands. Andernfalls die Abort-Prozedur wird nicht aufgerufen, und der Benutzer wird in der Lage, den Druckauftrag abbrechen.  
  
## <a name="print-preview-electronic-paper-with-user-interface"></a>Seitenansicht: Elektronischen Dokument mit Benutzeroberfläche  
 Seitenansicht, versucht, im Wesentlichen die Anzeige in eine Emulation eines Druckers zu aktivieren. Standardmäßig dient das den Clientbereich des Hauptfensters ein oder zwei Seiten vollständig innerhalb des Fensters angezeigt. Der Benutzer kann auf einen Bereich der Seite zur Anzeige im Detail zu vergrößern. Mit zusätzlicher Unterstützung kann der Benutzer auch so bearbeiten Sie das Dokument im Vorschaumodus zulässig sein.  
  
## <a name="customizing-print-preview"></a>Anpassen der Seitenansicht  
 Dieser Hinweis betrifft nur einen Aspekt der Seitenansicht ändern: Hinzufügen von UI in den Vorschaumodus wechseln. Weitere Änderungen möglich sind, jedoch solche Änderungen sind nicht Gegenstand dieser Diskussion.  
  
## <a name="to-add-ui-to-the-preview-mode"></a>Die im Vorschaumodus Benutzeroberfläche hinzu  
  
1.  Leiten Sie eine Klasse anzeigen von **CPreviewView**.  
  
2.  Fügen Sie Befehlshandler für die UI-Aspekte, die Sie wünschen.  
  
3.  Wenn Sie die Anzeige visuellen Aspekte hinzufügen, überschreiben `OnDraw` und führen Sie die Zeichnung nach dem Aufruf **CPreviewView::OnDraw.**  
  
## <a name="onfileprintpreview"></a>OnFilePrintPreview  
 Dies ist die Befehlshandler für die Seitenansicht. Die Standardimplementierung ist:  
  
```  
void CView::OnFilePrintPreview()  
{ *// In derived classes,
    implement special window handling here *// Be sure to Unhook Frame Window close if hooked.  
 *// must not create this on the frame. Must outlive this function  
    CPrintPreviewState* pState = new CPrintPreviewState;  
 
    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR,
    this,  
    RUNTIME_CLASS(CPreviewView),
    pState))  
 { *// In derived classes,
    reverse special window handling *// here for Preview failure case  
 
    TRACE0("Error: DoPrintPreview failed");

    AfxMessageBox(AFX_IDP_COMMAND_FAILURE);

 delete pState;      // preview failed to initialize, *// delete State now  
 }  
}  
```  
  
 **DoPrintPreview** im Hauptfenster der Anwendung werden ausgeblendet. Steuerleisten, z. B. die Statusleiste können beibehalten werden durch Angabe in der pState ->**DwStates** Member (Dies ist eine Bitmaske aus, und die Bits für einzelne Steuerleisten werden definiert, indem **AFX_CONTROLBAR_MASK**(AFX_IDW_MYBAR)). Das Fenster pState ->**nIDMainPane** ist das Fenster, das automatisch reshown und ausgeblendet werden soll. **DoPrintPreview** wird eine Schaltflächenleiste wird dann für die Preview-Benutzeroberfläche erstellt. Wenn Fenster besondere Behandlung erforderlich ist, z. B. ein- oder ausblenden anderen Fenstern, die vor dem erfolgen soll **DoPrintPreview** aufgerufen wird.  
  
 Standardmäßig, Seitenansicht abgeschlossen ist, wird die Steuerleisten an zurückgegeben den ursprünglichen Status und im Hauptfenster angezeigt. Wenn eine besondere Behandlung erforderlich ist, sollte es in einer Überschreibung von vorgenommen werden **EndPrintPreview.** Wenn **DoPrintPreview** ein Fehler auftritt, geben Sie auch eine besondere Behandlung.  
  
 DoPrintPreview wird mit aufgerufen:  
  
-   Ressourcen-ID der Dialogfeldvorlage für die Seitenansicht-Symbolleiste.  
  
-   Ein Zeiger auf die Sicht zum Ausführen der drucken für die Seitenansicht.  
  
-   Die Laufzeitklasse der Vorschauansicht-Klasse. Dies wird im DoPrintPreview dynamisch erstellt werden.  
  
-   Der Zeiger CPrintPreviewState. Beachten Sie, dass die CPrintPreviewState-Struktur (oder abgeleitete-Struktur, wenn die Anwendung weitere Zustand beibehalten) muss *nicht* auf den Frame erstellt werden. DoPrintPreview ist ohne Modus und bis EndPrintPreview aufgerufen wird, muss dieser Struktur Überleben.  
  
    > [!NOTE]
    >  Wenn Sie eine separate Ansicht oder Ansichtsklasse für druckunterstützung erforderlich ist, sollte ein Zeiger auf dieses Objekt als zweiten Parameter übergeben werden.  
  
## <a name="endprintpreview"></a>EndPrintPreview  
 Dies wird aufgerufen, um den Seitenansichtmodus zu beenden. Es ist häufig wünschenswert, wechseln zur Seite im Dokument, die zuletzt in der Seitenansicht angezeigt wurde. **EndPrintPreview** ist die Anwendung Gelegenheit dazu. Die "pInfo" ->`m_nCurPage` Member ist die Seite, die zuletzt (am weitesten links angezeigt wurden, wenn zwei Seiten angezeigt wurden, ist), und der Zeiger ist ein Hinweis auf, in dem auf der Seite der Benutzer möchte wurde. Da die Struktur der Sicht der Anwendung das Framework nicht bekannt ist, müssen Sie den Code so verschieben Sie in den ausgewählten Punkt bereitstellen.  
  
 Sie sollten die meisten Aktionen vor dem Aufruf **CView::EndPrintPreview**. Dieser Aufruf kehrt die Auswirkungen der **DoPrintPreview** und löscht pView, pDC und "pInfo".  
  
```  
// Any further cleanup should be done here.  
CView::EndPrintPreview(pDC,
    pInfo,
    point,
    pView);
```  
  
## <a name="cwinapponfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 Dies muss für das Menüelement Drucker einrichten zugeordnet werden. In den meisten Fällen ist es nicht notwendig, die Implementierung überschreiben.  
  
## <a name="page-nomenclature"></a>Seite "-Terminologie  
 Ein weiteres Problem ist der Seitennummerierung "und" Order. Für einfache Textverarbeitungsprogramm Anwendungen vom Typ ist dies ein Problem einfach. Die meisten Seitenansicht Systeme wird davon ausgegangen, dass jede gedruckte Seite einer Seite im Dokument entspricht.  
  
 Bei dem Versuch, eine allgemeine Lösung zu erstellen, gibt es einige Punkte zu berücksichtigen. Angenommen Sie, ein CAD-System. Der Benutzer hat eine Zeichnung, die mehrere E Größe Tabellen abdeckt. Eine E-Größe (oder eine kleinere skaliert) Plotter, Seitennummerierung wie im einfachen Fall wäre. Aber auf einem Laserdrucker drucken 16 A-Größe Seiten pro Blatt, was Seitenansicht berücksichtigt eine "Seite"  
  
 Wie in der einführenden Abschnitt angegeben, dient wie einen Drucker Seitenansicht. Aus diesem Grund wird der Benutzer angezeigt, was aus bestimmten Drucker eintreffen würde, die ausgewählt wird. Es liegt im Ermessen der Ansicht, um zu bestimmen, welches Bild auf jeder Seite gedruckt wird.  
  
 Die Seite Beschreibungszeichenfolge in die `CPrintInfo` Struktur bietet eine Möglichkeit die Seitenzahl für den Benutzer angezeigt, wenn es als eine Zahl pro Seite dargestellt werden kann (wie "Seite 1" oder "Seiten 1-2"). Diese Zeichenfolge wird verwendet, durch die standardmäßige Implementierung des **CPreviewView::OnDisplayPageNumber**. Bei Bedarf ein anderen Bildschirm wird möglicherweise eine dieser virtuelle Funktion, z. B. "" Sheet1 ", Abschnitte A, B" Bereitstellen überschreiben.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

