---
title: Mehrseitige Dokumente
ms.date: 11/19/2018
helpviewer_keywords:
- pagination [MFC]
- overriding [MFC], View class functions for printing
- OnPrepareDC method [MFC]
- CPrintInfo structure [MFC], multipage documents
- OnEndPrinting method [MFC]
- protocols [MFC], printing protocol
- document pages vs. printer pages [MFC]
- printer mode [MFC]
- printing [MFC], multipage documents
- printers [MFC], printer mode
- documents [MFC], printing
- OnPreparePrinting method [MFC]
- OnPrint method [MFC]
- DoPreparePrinting method and pagination [MFC]
- OnDraw method [MFC], printing
- pagination [MFC], printing multipage documents
- printing [MFC], protocol
- pages [MFC], printing
- OnBeginPrinting method [MFC]
- multipage documents [MFC]
- printing [MFC], pagination
- documents [MFC], paginating
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
ms.openlocfilehash: b4ec9f456443b9cd180f1558946829281bc10a36
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176379"
---
# <a name="multipage-documents"></a>Mehrseitige Dokumente

In diesem Artikel wird das Windows-Druck-Protokoll beschrieben und erläutert, wie zum Drucken von Dokumenten, die mehr als eine Seite enthalten. Der Artikel befasst sich in den folgenden Themen:

- [Druckprotokoll](#_core_the_printing_protocol)

- [View-Klassenfunktionen überschreiben](#_core_overriding_view_class_functions)

- [Die Paginierung](#_core_pagination)

- [Druckseiten im Vergleich zu Dokumentseite](#_core_printer_pages_vs.._document_pages)

- [Drucken-Time-Paginierung](#_core_print.2d.time_pagination)

##  <a name="_core_the_printing_protocol"></a> Das Protokoll für das Drucken

Um ein mehrseitiges Dokument zu drucken, interagieren das Framework und die Ansicht auf folgende Weise aus. Zunächst zeigt das Framework die **Drucken** im Dialogfeld erstellt einen Gerätekontext für den Drucker und ruft die [StartDoc](../mfc/reference/cdc-class.md#startdoc) Memberfunktion die [CDC](../mfc/reference/cdc-class.md) Objekt. Klicken Sie dann für jede Seite des Dokuments, das Framework Ruft die [StartPage](../mfc/reference/cdc-class.md#startpage) Memberfunktion die `CDC` Objekt, das Objekt auf der Seite, und klicken Sie auf Aufrufe drucken weist die [EndPage](../mfc/reference/cdc-class.md#endpage) Member-Funktion. Wenn der Druckermodus vor dem Starten einer bestimmten Seite geändert werden muss, ruft die Ansicht [ResetDC](../mfc/reference/cdc-class.md#resetdc), welche Updates die [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) Struktur, die den neuen Drucker-modusinformationen enthält. Wenn das gesamte Dokument gedruckt wurde, wird das Framework Ruft die [EndDoc](../mfc/reference/cdc-class.md#enddoc) Member-Funktion.

##  <a name="_core_overriding_view_class_functions"></a> View-Klassenfunktionen überschreiben

Die [CView](../mfc/reference/cview-class.md) -Klasse definiert mehrere Memberfunktionen, die während des Druckens durch das Framework aufgerufen werden. Indem Sie diese Funktionen in Ihrer Ansichtsklasse überschreiben, geben Sie die Verbindungen zwischen Drucklogik des Frameworks und Drucklogik Ihrer Ansichtsklasse. Die folgende Tabelle enthält diese Memberfunktionen.

### <a name="cviews-overridable-functions-for-printing"></a>CView überschreibbare-Funktionen für das Drucken

|name|Grund für das Überschreiben|
|----------|---------------------------|
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|Um Werte in das Dialogfeld Drucken, insbesondere die Länge des Dokuments einzufügen.|
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|Zuweisen von Schriftarten oder andere GDI-Ressourcen|
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|Attribute des Gerätekontexts für eine bestimmte Seite anpassen oder Sie Print-Time-Paginierung|
|[OnPrint](../mfc/reference/cview-class.md#onprint)|So drucken Sie eine bestimmte Seite|
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|Beim Aufheben der Zuordnung GDI-Ressourcen|

Drucken-spezifische Verarbeitung in anderen Funktionen auch möglich, aber diese Funktionen sind diejenigen, die den Druckvorgang zu steuern.

Die folgende Abbildung veranschaulicht die Schritte bei der Druckvorgang und zeigt, wo jede `CView`die Druck-Member-Funktionen aufgerufen werden. Im weiteren Verlauf dieses Artikels wird die meisten Schritte ausführlicher erläutert. Zusätzliche Teile des Druckvorgangs werden in diesem Artikel beschrieben [Zuordnen von GDI-Ressourcen](../mfc/allocating-gdi-resources.md).

![Drucken-schleifenprozess](../mfc/media/vc37c71.gif "druckschleifenprozess") <br/>
Druckschleife

##  <a name="_core_pagination"></a> Die Paginierung

Das Framework speichert ein Großteil der Informationen eines Druckauftrags in einer [CPrintInfo](../mfc/reference/cprintinfo-structure.md) Struktur. Einige der Werte in `CPrintInfo` beziehen sich auf die Paginierung; diese Werte zur Verfügung stehen, wie in der folgenden Tabelle gezeigt.

### <a name="page-number-information-stored-in-cprintinfo"></a>Seitenzahl Informationen in CPrintInfo

|Membervariablen oder<br /><br /> Name(n) der Funktion|Die Nummer der Seite auf die verwiesen wird|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|Erste Seite des Dokuments|
|`GetMaxPage`/`SetMaxPage`|Letzte Seite des Dokuments|
|`GetFromPage`|Erste Seite gedruckt werden sollen|
|`GetToPage`|Letzte Seite gedruckt werden sollen|
|`m_nCurPage`|Gegenwärtig gedruckte Seite|

Seitennummern beginnen bei 1, ist, also die erste Seite nummeriert, 1, der nicht 0 ist. Weitere Informationen zu diesen und anderen Mitgliedern der [CPrintInfo](../mfc/reference/cprintinfo-structure.md), finden Sie unter den *MFC-Referenz*.

Am Anfang des Druckvorgangs, das Framework ruft der Ansicht [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) Memberfunktion wird die Übergabe eines Zeigers auf eine `CPrintInfo` Struktur. Der Anwendungs-Assistent stellt eine Implementierung von `OnPreparePrinting` aufruft, [DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting), eine andere Memberfunktion von `CView`. `DoPreparePrinting` ist die Funktion, die zeigt das Dialogfeld "Drucken" an und erstellt einen Drucker-Gerätekontext.

Die Anwendung wissen nicht an diesem Punkt, wie viele Seiten im Dokument sind. Es verwendet die Standardwerte 1 bis 0xFFFF, für die Nummern der ersten und letzten Seite des Dokuments. Überschreiben, wenn Sie, wie viele Seiten Ihr Dokument verfügt wissen, `OnPreparePrinting` , und rufen Sie [SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage) für die `CPrintInfo` strukturieren, bevor Sie sie zum Senden `DoPreparePrinting`. Dadurch können Sie die Länge des Dokuments angeben.

`DoPreparePrinting` Anschließend zeigt das Dialogfeld "Drucken". Bei der Ausgabe der `CPrintInfo` Struktur enthält, die vom Benutzer angegebenen Werte. Wenn der Benutzer nur einen ausgewählten Bereich von Seiten zu drucken möchte, kann er oder sie die Start- und End Seitenzahlen im Dialogfeld "Drucken" angeben. Das Framework ruft diese Werte mithilfe der `GetFromPage` und `GetToPage` Funktionen [CPrintInfo](../mfc/reference/cprintinfo-structure.md). Wenn der Benutzer einen Seitenbereich angeben, nicht, das Framework ruft `GetMinPage` und `GetMaxPage` und verwendet die Werte, die zurückgegeben werden, um das gesamte Dokument zu drucken.

Das Framework Ruft für jede Seite eines Dokuments gedruckt werden sollen, zwei Memberfunktionen in Ihrer Ansichtsklasse [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) und [OnPrint](../mfc/reference/cview-class.md#onprint), und übergibt Sie jede Funktion zwei Parameter: einen Zeiger auf eine [ CDC](../mfc/reference/cdc-class.md) Objekt und einen Zeiger auf eine `CPrintInfo` Struktur. Jedes Mal, wenn das Framework ruft `OnPrepareDC` und `OnPrint`, übergibt einen anderen Wert in der *M_nCurPage* Mitglied der `CPrintInfo` Struktur. Auf diese Weise weist das Framework die Ansicht der Seite gedruckt werden soll.

Die [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) Member-Funktion wird auch für die Bildschirmanzeige verwendet. Es ist Anpassungen vor, um den Gerätekontext, vor dem darstellen. `OnPrepareDC` dient eine ähnliche Rolle beim Drucken, aber es eine Reihe von Unterschieden gibt: zuerst die `CDC` Objekt stellt einen druckergerätkontext anstelle von einem Bildschirm Gerätekontext und dann eine `CPrintInfo` Objekt als zweiten Parameter übergeben wird. (Dieser Parameter ist **NULL** beim `OnPrepareDC` für die Bildschirmanzeige aufgerufen wird.) Außer Kraft setzen `OnPrepareDC` , nehmen Sie Anpassungen vor, um den Gerätekontext, die basierend auf der Seite gedruckt wird. Sie können z. B. verschieben den Ursprung des Viewports und des Ausschneidebereichs um sicherzustellen, dass der entsprechende Teil des Dokuments gedruckt wird.

Die [OnPrint](../mfc/reference/cview-class.md#onprint) Memberfunktion führt das eigentliche Drucken der Seite. Der Artikel [wie Standard Drucken erfolgt](../mfc/how-default-printing-is-done.md) zeigt, wie das Framework ruft [OnDraw](../mfc/reference/cview-class.md#ondraw) mit einem Drucker-Gerätekontext zum Ausführen von drucken. Genauer gesagt: das Framework ruft `OnPrint` mit einem `CPrintInfo` Struktur und einen Gerätekontext und `OnPrint` übergibt den Gerätekontext zu `OnDraw`. Außer Kraft setzen `OnPrint` kein Rendering ausführen, die nur während des Druckens und nicht für die Bildschirmanzeige ausgeführt werden soll. Beispielsweise, um die Kopf- oder Fußzeilen drucken (finden Sie im Artikel [Kopf- und Fußzeilen](../mfc/headers-and-footers.md) Informationen). Rufen Sie anschließend `OnDraw` aus der Außerkraftsetzung der `OnPrint` , um das Rendering, die sowohl Bildschirmanzeige gemeinsam und drucken.

Die Tatsache, `OnDraw` führt das Rendern, für beide anzeigen Bildschirm und Drucken bedeutet, dass Ihre Anwendung WYSIWYG ist: "Anzeige ist was Sie erhalten." Angenommen Sie jedoch, dass Sie eine WYSIWYG-Anwendung schreiben, werden nicht aus. Angenommen Sie, einen Text-Editor, der fett formatierter Schrift für das Drucken verwendet jedoch Steuercode fett formatierter Text auf dem Bildschirm an. In diesem Fall verwenden Sie `OnDraw` ausschließlich für die Bildschirmanzeige. Wenn Sie außer Kraft setzen `OnPrint`, ersetzen Sie den Aufruf von `OnDraw` durch einen Aufruf an eine separate zeichnen-Funktion. Diese Funktion zeichnet das Dokument die Möglichkeit, auf Papier, mithilfe der Attribute, die auf dem Bildschirm angezeigt werden nicht angezeigt wird.

##  <a name="_core_printer_pages_vs.._document_pages"></a> Drucker-Seiten im Vergleich zu Dokumentseite

Wenn Sie auf die Seitenzahlen verweisen, ist es manchmal notwendig, zwischen des Druckers Konzept einer Seite und eines Dokuments das Konzept einer Seite zu unterscheiden. Aus Sicht des Druckers ist eine Seite ein Blatt Papier. Allerdings entspricht ein Blatt Papier nicht unbedingt eine Seite des Dokuments. Wenn Sie einen Newsletter, drucken, in denen die Blätter gefaltet werden sind, kann ein Blatt Papier z. B. den ersten und letzten Seite des Dokuments gleichzeitig enthalten. Auf ähnliche Weise, wenn Sie ein Arbeitsblatt drucken, nicht des Dokuments Seiten überhaupt bestehen. Stattdessen kann ein Blatt Papier Zeilen 1 bis 20, 6 bis 10-Spalten enthalten.

Alle Zahlen in der [CPrintInfo](../mfc/reference/cprintinfo-structure.md) Struktur finden Sie auf Druckseiten. Das Framework ruft `OnPrepareDC` und `OnPrint` einmal für jedes Blatt Papier, die den Drucker durchlaufen wird. Wenn Sie außer Kraft setzen der [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) Funktion, um die Länge des Dokuments angeben, müssen Sie Druckseiten. Wenn eine 1: 1-Entsprechung vorhanden ist (d. h. eine Druckerseite ist gleich eine Dokumentseite), ist dies einfach. Wenn Sie auf der anderen Seite Dokumentseiten und Druckerseiten nicht direkt entsprechen, müssen Sie zwischen diesen übersetzen. Betrachten Sie beispielsweise ein Arbeitsblatt drucken. Beim Überschreiben von `OnPreparePrinting`, müssen Sie berechnen, wie viele Blätter werden erforderlich, um den gesamten Ausdruck aus, und klicken Sie dann diesen Wert zu verwenden, beim Aufrufen der `SetMaxPage` Memberfunktion `CPrintInfo`. Auf ähnliche Weise beim Überschreiben von `OnPrepareDC`, müssen Sie übersetzen *M_nCurPage* in den Bereich von Zeilen und Spalten, die auf dem entsprechenden Blatt angezeigt, und klicken Sie dann den Ursprung des Viewports entsprechend anpassen.

##  <a name="_core_print.2d.time_pagination"></a> Drucken-Time-Paginierung

In einigen Fällen möglicherweise nicht Ihrer Ansichtsklasse im Voraus wissen wie lange das Dokument ist, bis er tatsächlich gedruckt wurde. Beispielsweise angenommen, Ihre Anwendung WYSIWYG nicht ist, nicht so Länge des Dokuments, auf dem Bildschirm seine Länge, die beim Drucken entsprechen.

Dies bewirkt, dass ein Problem beim Überschreiben [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) für Ihre Ansichtsklasse: Sie können keinen Wert, der übergeben der `SetMaxPage` Funktion der [CPrintInfo](../mfc/reference/cprintinfo-structure.md) Struktur, da Sie nicht, dass die Länge des wissen eine Dokument. Wenn der Benutzer eine Seitenzahl, die mithilfe des Dialogfelds drucken aufhören vorgibt, weiß nicht das Framework bei die print-Schleife zu beenden. Die einzige Möglichkeit, um zu bestimmen, wann die print-Schleife beendet ist, drucken Sie das Dokument, und sehen, wenn sie endet. Die Ansichtsklasse muss für das Ende des Dokuments überprüfen, während es gedruckt wird, und klicken Sie dann das Framework zu benachrichtigen, wenn das Ende erreicht ist.

Das Framework basiert auf einer Ihrer Ansichtsklasse [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) Funktion anzuweisen, wann beendet werden. Nach jedem Anruf `OnPrepareDC`, das Framework prüft ein Mitglied der `CPrintInfo` Struktur mit dem Namen *M_bContinuePrinting*. Der Standardwert ist **"true".** Solange es bleibt also das Framework die print-Schleife fortgesetzt wird. Wenn sie, um festgelegt ist **"false"**, das Framework beendet wird. Zum Drucken durchführen, außer Kraft setzen `OnPrepareDC` zu überprüfen, ob das Ende des Dokuments erreicht, festgelegt und wurde *M_bContinuePrinting* zu **"false"** hat er.

Die standardmäßige Implementierung des `OnPrepareDC` legt *M_bContinuePrinting* zu **"false"** , wenn die aktuelle Seite größer als 1 ist. Dies bedeutet, dass die Länge des Dokuments angegeben, wird das Framework davon ausgegangen, dass das Dokument eine Seite lang ist. Eine Folge davon ist, dass Sie darauf achten müssen, wenn Sie die Basisklassenversion von Aufrufen `OnPrepareDC`. Gehen Sie, die nicht *M_bContinuePrinting* werden **"true"** nach dem Aufrufen der Basisklassenversion.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Kopf- und Fußzeilen](../mfc/headers-and-footers.md)

- [Zuordnen von GDI-Ressourcen](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>Siehe auch

[Drucken](../mfc/printing.md)<br/>
[CView-Klasse](../mfc/reference/cview-class.md)<br/>
[CDC-Klasse](../mfc/reference/cdc-class.md)