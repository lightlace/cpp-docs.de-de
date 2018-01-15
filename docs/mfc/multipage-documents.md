---
title: Mehrseitige Dokumente | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43bc9bbe4653e34c37ae46439baa1e649d6d8042
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="multipage-documents"></a>Mehrseitige Dokumente
In diesem Artikel wird beschrieben, die Windows-Druckprotokoll und erläutert, wie zum Drucken von Dokumenten, die über mehrere Seiten enthalten. Die Artikel werden die folgenden Themen behandelt:  
  
-   [Druckprotokoll](#_core_the_printing_protocol)  
  
-   [View-Klassenfunktionen überschreiben](#_core_overriding_view_class_functions)  
  
-   [Paginierung](#_core_pagination)  
  
-   [Druckseiten im Vergleich zu Dokumentseite](#_core_printer_pages_vs.._document_pages)  
  
-   [Drucken-Time-Paginierung](#_core_print.2d.time_pagination)  
  
##  <a name="_core_the_printing_protocol"></a>Das Protokoll für das Drucken  
 Interagieren zum Drucken eines mehrseitigen Dokuments vom Framework als auch anzeigen, auf folgende Weise. Vom Framework zuerst angezeigt wird der **Drucken** (Dialogfeld), erstellt einen Gerätekontext für den Drucker, und ruft die [StartDoc](../mfc/reference/cdc-class.md#startdoc) Memberfunktion der [CDC](../mfc/reference/cdc-class.md) Objekt. Klicken Sie dann für jede Seite des Dokuments, das Framework Ruft die [StartPage](../mfc/reference/cdc-class.md#startpage) Memberfunktion von der `CDC` Objekt, weist das Ansichtsobjekt So drucken Sie die Seite, und ruft die [EndPage](../mfc/reference/cdc-class.md#endpage) Memberfunktion. Wenn der Druckermodus geändert werden muss, bevor Sie eine bestimmte Seite starten die Sicht aufruft [ResetDC](../mfc/reference/cdc-class.md#resetdc), welche Updates die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Struktur, die den neuen Drucker-modusinformationen enthält. Wenn das gesamte Dokument gedruckt wurde, wird das Framework Ruft die [EndDoc](../mfc/reference/cdc-class.md#enddoc) Memberfunktion.  
  
##  <a name="_core_overriding_view_class_functions"></a>View-Klassenfunktionen überschreiben  
 Die [CView](../mfc/reference/cview-class.md) Klasse definiert mehrere Memberfunktionen, die während des Druckens durch das Framework aufgerufen werden. Indem Sie diese Funktionen in Ihrer Ansichtsklasse überschreiben, geben Sie die Verbindungen zwischen dem Framework drucken Logik und Drucken Logik Ihrer Ansichtsklasse. In der folgenden Tabelle sind diese Memberfunktionen aufgeführt.  
  
### <a name="cviews-overridable-functions-for-printing"></a>CView überschreibbare-Funktionen für das Drucken  
  
|name|Grund zum Überschreiben|  
|----------|---------------------------|  
|[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)|Um Werte in das Dialogfeld Drucken, insbesondere die Länge des Dokuments einzufügen.|  
|[OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting)|Zuweisen von Schriftarten oder andere GDI-Ressourcen|  
|[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)|Attribute des Gerätekontexts für eine angegebene Seite anpassen, oder Drucken Zeit Paginierung durchführen|  
|[OnPrint](../mfc/reference/cview-class.md#onprint)|So drucken Sie eine bestimmte Seite|  
|[OnEndPrinting](../mfc/reference/cview-class.md#onendprinting)|Beim Aufheben der Zuweisung GDI-Ressourcen|  
  
 Drucken-spezifische Verarbeitung in anderen Funktionen als auch möglich, aber diese Funktionen sind diejenigen Argumente, die den Druckvorgang Laufwerk.  
  
 Die folgende Abbildung veranschaulicht die Schritte des Druckvorgangs und erfahren, wo jede `CView`des drucken Member-Funktionen aufgerufen werden. Im weiteren Verlauf dieses Artikels wird die meisten Schritte ausführlicher erläutert. Zusätzliche Teile des Druckvorgangs werden im Artikel beschriebenen [Zuordnen von GDI-Ressourcen](../mfc/allocating-gdi-resources.md).  
  
 ![Drucken von schleifenprozess](../mfc/media/vc37c71.gif "vc37c71")  
Druckschleife  
  
##  <a name="_core_pagination"></a>Paginierung  
 Das Framework speichert ein Großteil der Informationen eines Druckauftrags in einer [CPrintInfo](../mfc/reference/cprintinfo-structure.md) Struktur. Einige der Werte in `CPrintInfo` beziehen sich auf die Paginierung; diese Werte ist möglich, wie in der folgenden Tabelle gezeigt.  
  
### <a name="page-number-information-stored-in-cprintinfo"></a>In CPrintInfo gespeicherten Seitenzahl-Informationen  
  
|Membervariablen gespeichert oder<br /><br /> Funktion/r/s|Seitenzahl, die auf die verwiesen wird|  
|-----------------------------------------------|----------------------------|  
|`GetMinPage`/`SetMinPage`|Erste Seite des Dokuments|  
|`GetMaxPage`/`SetMaxPage`|Letzte Seite des Dokuments|  
|`GetFromPage`|Erste Seite gedruckt werden|  
|`GetToPage`|Letzte Seite gedruckt werden|  
|`m_nCurPage`|Gerade gedruckte Seite|  
  
 Seitennummern beginnen mit 1 nummeriert, also die erste Seite 1, nicht 0 ist. Weitere Informationen zu diesen und anderen Mitgliedern der [CPrintInfo](../mfc/reference/cprintinfo-structure.md), finden Sie unter der *MFC-Referenz*.  
  
 Am Anfang des Druckvorgangs das Framework ruft der Sicht [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) Memberfunktion, die Übergabe eines Zeigers auf eine `CPrintInfo` Struktur. Der Anwendungs-Assistent stellt eine Implementierung von `OnPreparePrinting` damaligen [DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting), eine andere Memberfunktion der `CView`. `DoPreparePrinting`ist die Funktion, die zeigt das Dialogfeld "Drucken" und erstellt einen Drucker-Gerätekontext.  
  
 Zu diesem Zeitpunkt weiß nicht, die Anwendung wie viele Seiten im Dokument sind. Die Standardwerte 1 und 0xFFFF verwendet für die Nummern der ersten und letzten Seite des Dokuments. Überschreiben, wenn Sie, wie viele Seiten Ihr Dokument wurde wissen, `OnPreparePrinting` , und rufen Sie [SetMaxPage]--brokenlink--(reference/cprintinfo-class.md#setmaxpage) für die `CPrintInfo` strukturieren, bevor Sie sie zum Senden `DoPreparePrinting`. Dadurch können Sie die Länge des Dokuments angeben.  
  
 `DoPreparePrinting`Anschließend zeigt das Dialogfeld Drucken. Bei der `CPrintInfo` Struktur enthält die vom Benutzer angegebenen Werte. Wenn der Benutzer nur einen ausgewählten Bereich von Seiten drucken möchte, kann er oder sie die Start- und End Seitenzahlen im Dialogfeld "Drucken" angeben. Das Framework ruft diese Werte mithilfe der `GetFromPage` und `GetToPage` Funktionen [CPrintInfo](../mfc/reference/cprintinfo-structure.md). Wenn der Benutzer einen Seitenbereich angeben, nicht, das Framework ruft `GetMinPage` und `GetMaxPage` und verwendet die Werte, die zurückgegeben werden, um das gesamte Dokument zu drucken.  
  
 Das Framework Ruft für jede Seite eines Dokuments gedruckt werden zwei Memberfunktionen in Ihrer Ansichtsklasse [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) und [OnPrint](../mfc/reference/cview-class.md#onprint), und übergibt Sie jede Funktion zwei Parameter: einen Zeiger auf eine [ CDC](../mfc/reference/cdc-class.md) Objekt und einen Zeiger auf eine `CPrintInfo` Struktur. Jedes Mal, wenn das Framework ruft `OnPrepareDC` und `OnPrint`, übergibt einen anderen Wert in der `m_nCurPage` Mitglied der `CPrintInfo` Struktur. Auf diese Weise weist das Framework die Ansicht der Seite gedruckt werden soll.  
  
 Die [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) Memberfunktion wird auch für die Bildschirmanzeige verwendet. Außerdem wird anpassen, um den Gerätekontext, bevor Zeichnung stattfindet. `OnPrepareDC`eine ähnliche Rolle beim Drucken, dient, aber es einige Unterschiede gibt: zuerst die `CDC` Objekt stellt einen druckergerätkontext anstelle einer Bildschirm Gerätekontext und die zweite, eine `CPrintInfo` Objekt wird als zweiter Parameter übergeben. (Dieser Parameter ist **NULL** Wenn `OnPrepareDC` für die Bildschirmanzeige aufgerufen wird.) Überschreiben Sie `OnPrepareDC` vornehmen von Korrekturen für den Gerätekontext, der basierend auf der Seite gedruckt wird. Verschieben Sie z. B. den Ursprung des Viewports mit des Clippingbereichs, um sicherzustellen, dass der entsprechende Teil des Dokuments gedruckt wird.  
  
 Die [OnPrint](../mfc/reference/cview-class.md#onprint) Memberfunktion führt das eigentliche Drucken der Seite. Der Artikel [wie Standard Drucken erfolgt](../mfc/how-default-printing-is-done.md) wird gezeigt, wie das Framework ruft [OnDraw](../mfc/reference/cview-class.md#ondraw) mit einem Drucker-Gerätekontext zum Ausführen von drucken. Genauer gesagt, das Framework ruft `OnPrint` mit einem `CPrintInfo` Struktur und einen Gerätekontext und `OnPrint` übergibt den Gerätekontext `OnDraw`. Überschreiben Sie `OnPrint` jeder Rendering ausführen, die nur während des Druckens und nicht für die Bildschirmanzeige erfolgen soll. Z. B. Kopf- oder Fußzeilen drucken (finden Sie im Artikel [Kopf- und Fußzeilen](../mfc/headers-and-footers.md) für Weitere Informationen). Rufen Sie anschließend `OnDraw` aus der Überschreibung der `OnPrint` das Rendering, die sowohl Bildschirmanzeige gemeinsam und drucken möchten.  
  
 Die Tatsache, `OnDraw` ist das Rendering für beide anzeigen Bildschirm und Drucken bedeutet, dass Ihre Anwendung WYSIWYG ist: "Was Sie sehen, ist what you get." Nehmen Sie jedoch an, dass Sie eine WYSIWYG-Anwendung schreiben, sind nicht. Angenommen Sie, einen Text-Editor, der fett formatierter Schrift für das Drucken verwendet, aber Steuerungscodes an, dass fett formatierter Text auf dem Bildschirm angezeigt. Verwenden Sie in einer solchen Situation `OnDraw` ausschließlich für die Bildschirmanzeige. Wenn Sie außer Kraft setzen `OnPrint`, ersetzen Sie durch den Aufruf von `OnDraw` durch einen Aufruf an eine separate zeichnen-Funktion. Diese Funktion zeichnet das Dokument wie er angezeigt, auf Papier wird, verwenden die Attribute, die nicht auf dem Bildschirm angezeigt werden.  
  
##  <a name="_core_printer_pages_vs.._document_pages"></a>Drucker-Seiten im Vergleich zu Dokumentseite  
 Wenn Sie auf die Seitenzahlen verweisen, ist es manchmal notwendig zur Unterscheidung zwischen den Drucker Konzept einer Seite und des Dokuments Konzept einer Seite. Aus Sicht des Druckers ist eine Seite jeweils ein Blatt Papier an. Allerdings entspricht einem Blatt Papier nicht unbedingt eine Seite des Dokuments. Angenommen, wenn Sie einen Newsletter, drucken, in dem die Blätter gefaltet angezeigt werden sollen, jeweils ein Blatt Papier der ersten und letzten Seite des Dokuments, nebeneinander angezeigt werden enthält. Auf ähnliche Weise, wenn Sie ein Arbeitsblatt drucken, nicht das Dokument aus Seiten überhaupt bestehen. Stattdessen enthalten jeweils ein Blatt Papier Zeilen 1 bis 20 und die Spalten 6 bis 10.  
  
 Alle Seitenzahlen der [CPrintInfo](../mfc/reference/cprintinfo-structure.md) Struktur finden Sie in Seiten. Das Framework ruft `OnPrepareDC` und `OnPrint` einmal für jedes Blatt Papier, die den Drucker durchlaufen wird. Beim Überschreiben der [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) Funktion, um die Länge des Dokuments angeben, müssen Sie Seiten verwenden. Wenn eine 1: 1-Entsprechung vorhanden ist (d. h. seitenweise Drucker entspricht eine Dokumentseite), ist dies einfach. Wenn andererseits, Dokument und Druckseiten nicht direkt entsprechen, müssen Sie dazwischen übersetzen. Betrachten Sie beispielsweise eine Kalkulationstabelle zu drucken. Zum Überschreiben `OnPreparePrinting`, müssen Sie berechnen, wie viele Blätter werden erforderlich, um den gesamten Ausdruck, und klicken Sie dann diesen Wert verwenden, beim Aufrufen der `SetMaxPage` Memberfunktion von `CPrintInfo`. Auf ähnliche Weise zum Überschreiben `OnPrepareDC`, müssen Sie übersetzen `m_nCurPage` in den Bereich von Zeilen und Spalten, die auf dem entsprechenden Blatt angezeigt, und klicken Sie dann den Ursprung des Viewports entsprechend anpassen.  
  
##  <a name="_core_print.2d.time_pagination"></a>Drucken-Time-Paginierung  
 In einigen Situationen wissen Ihrer Ansichtsklasse nicht im voraus, wie lange das Dokument ist, bis es tatsächlich gedruckt wurde. Beispielsweise angenommen, Ihre Anwendung nicht WYSIWYG ist, nicht so Dokumentlänge auf dem Bildschirm seine Länge gedruckt entsprechen.  
  
 Dies bewirkt, dass ein Problem beim Überschreiben [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) für Ihre Ansichtsklasse: nicht möglich, übergeben Sie den Wert auf die `SetMaxPage` Funktion der [CPrintInfo](../mfc/reference/cprintinfo-structure.md) -Struktur, da Sie nicht, dass die Länge des wissen ein Dokument. Wenn der Benutzer eine Seitenzahl, beenden Sie mithilfe des Dialogfelds Drucken nicht, weiß nicht, das Framework wann die Druckschleife beendet werden soll. Die einzige Möglichkeit zum Ermitteln, wann die Druckschleife beendet besteht darin, das Dokument zu drucken und finden am Ende des Vorgangs. View-Klasse muss für das Ende des Dokuments überprüfen, während es ausgegeben wird, und teilen Sie anschließend das Framework beim Erreichen des Endes.  
  
 Das Framework stützt sich auf Ihrer Ansichtsklasse [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) Funktion anzuweisen, wann beendet werden soll. Nach jedem Anruf `OnPrepareDC`, das Framework Hier wird überprüft, ob ein Mitglied der `CPrintInfo` Struktur mit dem Namen `m_bContinuePrinting`. Der Standardwert ist **"true".** Solange sie ist daher das Framework die Drucken-Schleife fortgesetzt wird. Wenn sie, um festgelegt ist **"false"**, das Framework beendet. Zum Ausführen von Print-Time-Paginierung überschreiben `OnPrepareDC` zu überprüfen, ob das Ende des Dokuments erreicht, festgelegt und wurde `m_bContinuePrinting` auf **"false"** hat er.  
  
 Die standardmäßige Implementierung des `OnPrepareDC` legt `m_bContinuePrinting` auf **"false"** , wenn die aktuelle Seite größer als 1 ist. Dies bedeutet, dass wenn die Länge des Dokuments nicht angegeben wurde, wird das Framework davon ausgegangen, dass das Dokument eine Seite lang ist. Eine Folge davon ist, dass Sie darauf achten müssen, wenn Sie die Basisklassenversion von Aufrufen `OnPrepareDC`. Führen Sie nicht davon ausgehen, dass `m_bContinuePrinting` werden **"true"** nach dem Aufrufen der Basisklassenversion.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Kopf- und Fußzeilen](../mfc/headers-and-footers.md)  
  
-   [Zuordnen von GDI-Ressourcen](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Drucken](../mfc/printing.md)   
 [CView-Klasse](../mfc/reference/cview-class.md)   
 [CDC-Klasse](../mfc/reference/cdc-class.md)