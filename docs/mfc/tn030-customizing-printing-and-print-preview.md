---
title: "TN030: Anpassen des Druckvorgangs und der Druckvorschau"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.print"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anpassen des Druckvorgangs und der Druckvorschau"
  - "Seitenansicht, Anpassen"
  - "Drucken [MFC], Ansichten"
  - "Druckansichten"
  - "TN030"
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# TN030: Anpassen des Druckvorgangs und der Druckvorschau
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt den Prozess des Anpassens des Drucks und der Druckvorschau und beschreibt die Zwecke der Rückrufroutinen, die in `CView` verwendet und der Rückrufroutinen und der Memberfunktionen von **CPreviewView**.  
  
## Das Problem  
 MFC bietet eine vollständige Lösung für die meisten Drucks\- und Seitenansichtsanforderungen bereit.  In den meisten Fällen ist wenig Code benötigt, eine Ansicht zu haben, die in der Lage ist zu drucken und sich in der Vorschau anzuzeigen.  Es gibt es Verfahren, Drucken zu optimieren, die wichtigsten Aufwand beim Entwicklers erfordern, sowie einige Anwendungen müssen bestimmten Benutzeroberflächenelementen dem Seitenansicht hinzufügen.  
  
## Durch effiziente Drucken  
 Wenn Drucken einer MFC\-Anwendung mithilfe von Standardmethoden, Windows alle grafischen Geräteschnittstelle\- \(GDI\)\- Ausgabeaufrufe auf eine Metadatei im Arbeitsspeicher verweisen.  Wenn `EndPage` aufgerufen wird, wird Windows der Metadatei einmal für jedes physische Band erneut, das der Drucker erfordert, eine Seite zu drucken.  Während dieses Renderings fragt GDI häufig die Abbruchprozedur ab, um zu bestimmen, wenn sie weiter.  Normalerweise können die Abbruchprozedur die Verarbeitung von Meldungen, sodass der Benutzer den Druckauftrag mithilfe eines Druckdialogfelds abbrechen kann.  
  
 Leider ist dieses den Druckvorgang verlangsamen.  Wenn der Ausgabe in der Anwendung als der schnelle sein muss, wobei Standardtechnik erreicht werden kann, müssen Sie manuelle Streifenbildung implementieren.  
  
## Druckband  
 Um manuell mit einem Band bereitzustellen, müssen Sie die Druckschleife erneut implementieren dass `OnPrint` mehrmals pro Seite aufgerufen wird \(einmal pro Band\).  Die Druckschleife wird in der Funktion **OnFilePrint** in viewprnt.cpp implementiert.  In dem von `CView` abgeleiteten Klasse, überladen Sie diese Funktion, damit der Eintrag in der Meldungszuordnung für Behandlung der Druckbefehl die Druckfunktion aufruft.  Kopieren Sie die **OnFilePrint** Routine und ändern Sie die Druckschleife, um Streifenbildung zu implementieren.  Sie möchten wahrscheinlich auch das Streifenbildungsrechteck den Druck zu übergeben, damit Sie Zeichnung auf Grundlage den Abschnitt der Seite zur Optimierung, die gedruckt wird.  
  
 Zweitens müssen Sie `QueryAbort` beim Zeichnen des Bands oft aufrufen.  Andernfalls wird die Abbruchprozedur nicht aufgerufen und der Benutzer ist nicht möglich, den Druckauftrag abbrechen.  
  
## Seitenansicht: Elektronisches Papier mit Benutzeroberfläche  
 Seitenansicht im Wesentlichen Versuche, um die Anzeige zu einer Emulation eines Druckers zu machen.  Standardmäßig wird der Clientbereich des Hauptfensters verwendet, um eine oder zwei Seiten im Fenster vollständig anzuzeigen.  Der Benutzer kann in der Lage, auf der Seite einen Bereich vergrößern, um diese ausführlicher zu finden.  Mit zusätzlichen Unterstützung wird dem Benutzer sogar können, um das Dokument in der Seitenansicht zu bearbeiten.  
  
## Anpassen der Seitenansicht  
 Dieser Hinweis wird nur von einem Aspekt des Änderns der Seitenansicht: Hinzufügen von Benutzeroberfläche in der Seitenansicht.  Andere Änderungen möglich, diese Änderungen wurden näher beschrieben.  
  
## So Benutzeroberfläche dem Seitenansicht hinzufügen  
  
1.  Ableiten einer Ansichtsklasse von **CPreviewView**.  
  
2.  Fügen Sie Befehlshandlern für die Benutzeroberflächenaspekte hinzu, die Sie suchen.  
  
3.  Wenn Sie die visuellen Aspekte zur Anzeige hinzufügen, überschreiben Sie `OnDraw` und übergeben Sie die Zeichnung aus, nachdem Sie **CPreviewView::OnDraw.** aufgerufen haben  
  
## OnFilePrintPreview  
 Dies ist der Befehlshandler für Info\-Seitenansicht.  Die Standardimplementierung ist:  
  
```  
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
        delete pState;      // preview failed to initialize,   
                    // delete State now  
    }  
}  
```  
  
 **DoPrintPreview** blendet den Hauptbereich der Anwendung aus.  Steuerleisten, wie die Statusleiste, können beibehalten werden, indem sie im pState\-\>**dwStates**\-Member angibt \(dies ist eine Bitmaske und die Bits für einzelne Steuerleisten werden von **AFX\_CONTROLBAR\_MASK**\(AFX\_IDW\_MYBAR\)\) definiert.  Das Fenster pState\-\>**nIDMainPane** ist das Fenster, das automatisch reshown und ausgeblendet wird.  **DoPrintPreview** erstellt dann eine Schaltflächenleiste für die Standardvorschau Benutzeroberfläche.  Wenn speziell, wird Fensterbehandlung, wie erforderlich, um andere Fenster anzuzeigen oder auszublenden, die ausgeführt werden, bevor **DoPrintPreview** aufgerufen wird.  
  
 Beim Seitenansicht beendet, gibt sie den Steuerleisten zu den ursprünglichen Status und den Hauptbereich zu sichtbarem zurück.  Wenn andererseits benötigt wird, sollte sie in einer Überschreibung von **EndPrintPreview.** erfolgen Wenn **DoPrintPreview** fehlschlägt, stellen Sie auch besondere Behandlung bereit.  
  
 DoPrintPreview wird mit aufgerufen:  
  
-   Die Ressourcen\-ID der Dialogfeldvorlage für die Vorschausymbolleiste.  
  
-   Ein Zeiger auf die Ansicht, um das Drucken für die Seitenansicht auszuführen.  
  
-   Die der Laufzeitklasse Vorschau\-Ansichtsklasse.  Dies wird in DoPrintPreview dynamisch erstellt.  
  
-   Der CPrintPreviewState\-Zeiger.  Beachten Sie, dass die CPrintPreviewState\-Struktur \(oder die abgeleitete Struktur, wenn die Anwendung mehr beibehaltenen Zustand benötigt\), *nicht* über den Frame erstellt werden.  DoPrintPreview ist nicht modale und diese Struktur muss überleben, bis EndPrintPreview aufgerufen wird.  
  
    > [!NOTE]
    >  Wenn eine Ansicht oder eine separate Ansichtsklasse zum Drucken der Unterstützung erforderlich ist, sollte ein Zeiger auf dieses Objekt als zweiten Parameter übergeben werden.  
  
## EndPrintPreview  
 Dieses wird aufgerufen, um den der Seitenansicht zu beenden.  Sich blättern ist häufig wünschenswert, zur Seite im Dokument, die zuletzt in der Seitenansicht angezeigt wurde.  **EndPrintPreview** ist die Gefahr der Anwendung, das verwendet.  Der `m_nCurPage` pInfo\-\>Member ist die Seite, die zuletzt angezeigt wurde \(ganz links steht, wenn zwei Seiten angezeigt wurden\), und der Mauszeiger ist ein Hinweis auf, das auf der Seite " Benutzer interessiert war.  Da die Struktur der Ansicht der Anwendung dem Framework unbekannt, müssen Sie den Code um zum ausgewählten Punkt bereitstellen.  
  
 Sie sollten die meisten Aktionen ausführen, bevor Sie **CView::EndPrintPreview** aufrufen.  Dieser Aufruf kehrt die Effekte von **DoPrintPreview** und löscht pView, pDC und pInfo.  
  
```  
// Any further cleanup should be done here.  
CView::EndPrintPreview(pDC, pInfo, point, pView);  
```  
  
## CWinApp::OnFilePrintSetup  
 Dies muss für das Drucks\-Setupmenüelement zugeordnet werden.  In den meisten Fällen ist es nicht notwendig, die Implementierung zu überschreiben.  
  
## Seiten\-Nomenklatur  
 Andere Thema ist das der Seitenzahl und der Reihenfolge.  Für einfache Textverarbeitungsprogrammtyp\-Anwendungen ist dieses ein einfaches Problem.  Die meisten Seitenansichtssysteme nehmen an, dass jede gedruckte Seite zu einer Seite im Dokument entspricht.  
  
 Wenn Sie versuchen, eine generalisierte Projektmappe bereitzustellen, gibt jedoch mehrere Punkte zu berücksichtigen.  Stellen Sie sich ein CAD\-System vor.  Der Benutzer hat eine Zeichnungs\-, die einige E\-Größenblätter abdeckt.  Auf einem Plotter der E\-Größe \(oder einem kleineren, skaliert\) würde Seitenzahl wie im einfachen Fall sein.  Wenn auf einem Laserdrucker, 16 Ein\-Größenseiten pro Blatt installiertes, was enthält Druckvorschau für eine "Seite"?  
  
 Wie die einführenden Absatzzustände Seitenansicht, wie einen Drucker reagiert.  Daher sieht der Benutzer, was aus bestimmten Drucker herauskommen würde, der ausgewählt wird.  Er entspricht zur Ansicht, festzustellen, welches Bild auf jeder Seite auf.  
  
 Die Seitenbeschreibungszeichenfolge `CPrintInfo` in der Struktur enthält Ressourcen des Anzeigens der Seitenzahl für die Benutzer, wenn sie als eine Zahl pro Seite dargestellt werden kann \(z "in Seite 1 " oder "in den Seiten 1\-2"\). Diese Zeichenfolge wird durch die Standardimplementierung von **CPreviewView::OnDisplayPageNumber** verwendet.  Wenn eine andere Anzeige benötigt wird, überschreibt möglicherweise wie die virtuelle Funktion, um beispielsweise "Sheet1, Abschnitte A, B" bereitzustellen.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)