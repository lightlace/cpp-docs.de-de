---
title: "Mehrseitige Dokumente | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintInfo-Struktur, Mehrseitige Dokumente"
  - "Dokumentseiten und Druckerseiten"
  - "Dokumente, Paginierung"
  - "Dokumente, Drucken"
  - "DoPreparePrinting-Methode und Paginierung"
  - "Mehrseitige Dokumente"
  - "OnBeginPrinting-Methode"
  - "OnDraw-Methode, Drucken"
  - "OnEndPrinting-Methode"
  - "OnPrepareDC-Methode"
  - "OnPreparePrinting-Methode"
  - "OnPrint-Methode"
  - "Überschreiben, View-Klassenfunktionen für Drucken"
  - "Seiten, Drucken"
  - "Paginierung"
  - "Paginierung, Drucken von mehrseitige Dokumenten"
  - "Druckermodus"
  - "Drucker, Druckermodus"
  - "Drucken [MFC], Mehrseitige Dokumente"
  - "Drucken [MFC], Paginierung"
  - "Drucken [MFC], Protokoll"
  - "Protokolle, Druckprotokoll"
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Mehrseitige Dokumente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt Windows, das Protokoll gibt und beschreibt, wie Dokumente drucken, die mehr als einer Seite enthalten.  Der Artikel enthält die folgenden Themen:  
  
-   [Drucken des Protokolls](#_core_the_printing_protocol)  
  
-   [Überschreiben Ansichtsklassenfunktionen](#_core_overriding_view_class_functions)  
  
-   [Paginierung](#_core_pagination)  
  
-   [Druckerseiten für Dokumentseiten](#_core_printer_pages_vs.._document_pages)  
  
-   [Druck\-Zeitpaginierung](#_core_print.2d.time_pagination)  
  
##  <a name="_core_the_printing_protocol"></a> Das Drucks\-Protokoll  
 So ein mehrseitiges Dokument, dem Framework und Ansicht drucken interaktiv in der folgenden Weise.  Anfangs wird das Framework das Dialogfeld **Drucken** an, erstellt einen Gerätekontext für den Drucker und ruft die [StartDoc](../Topic/CDC::StartDoc.md)\-Memberfunktion des Objekts auf [CDC](../mfc/reference/cdc-class.md).  Dann werden für jede Seite des Dokuments, ruft das Framework die [StartPage](../Topic/CDC::StartPage.md)`CDC`\-Memberfunktion des Objekts auf, weist das Ansichtsobjekt an, um sie zu drucken und ruft die [EndPage](../Topic/CDC::EndPage.md)\-Memberfunktion auf.  Wenn der Druckermodus geändert werden muss, bevor eine bestimmte Seite beginnt, wird die Ansicht die [ResetDC](../Topic/CDC::ResetDC.md) auf, die die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)\-Struktur aktualisiert, die den neuen Druckermodusinformationen enthält.  Wenn das gesamte Dokument gedruckt wurde, ruft das Framework die Memberfunktion [EndDoc](../Topic/CDC::EndDoc.md) auf.  
  
##  <a name="_core_overriding_view_class_functions"></a> Überschreiben Ansichtsklassen\-Funktionen  
 Die [CView](../mfc/reference/cview-class.md)\-Klasse definiert mehrere Memberfunktionen, die durch das Framework während des Druckens aufgerufen werden.  Wenn Sie diese Funktionen in der Ansichtsklasse überschreiben, stellen Sie die Verbindungen zwischen der Drucklogik druckenden Logik des Frameworks und der Ansichtsklasse bereit.  Die folgende Tabelle zeigt dieser Memberfunktionen auf.  
  
### CViews überschreibbare Funktionen zum Drucken  
  
|Name|Grund für das Überschreiben|  
|----------|---------------------------------|  
|[OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)|Weitere Werte im Dialogfeld Drucken einfügen, insbesondere die Länge des Dokuments|  
|[OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)|So Schriftarten oder anderen GDI\-Ressourcen zuordnen|  
|[OnPrepareDC](../Topic/CView::OnPrepareDC.md)|Um Attribute des Gerätekontexts auf eine angegebene Seite anpassen, oder DruckZeitpaginierung ausführen|  
|[OnPrint](../Topic/CView::OnPrint.md)|Um eine bestimmte Seite drucken|  
|[OnEndPrinting](../Topic/CView::OnEndPrinting.md)|So GDI\-Ressourcen freigeben|  
  
 Sie können Druck\-verknüpftes in anderen auch Funktionen verarbeiten ausführen, aber diese Funktionen sind die, die den Druckvorgang steuern.  
  
 Die folgende Abbildung zeigt die Schritte, die in den Druckvorgang gehören und wird, wobei jedes von `CView`\-Memberfunktionen, das gedruckt wird, aufgerufen werden.  Der Rest dieses Artikels werden die meisten Schritte ausführlicher beschrieben.  Zusatzteile des Druckvorgangs werden im Artikel [Zuordnen von GDI\-Ressourcen](../mfc/allocating-gdi-resources.md) beschrieben.  
  
 ![Druckschleifenprozess](../mfc/media/vc37c71.png "vc37C71")  
Druckschleife  
  
##  <a name="_core_pagination"></a> Paginierung  
 Das Framework speichert viele der Informationen über ein Druckauftrag in einer [CPrintInfo](../mfc/reference/cprintinfo-structure.md)\-Struktur.  Verschiedene der Werte in `CPrintInfo` betreffen Paginierung; diese Werte sind wie in der folgenden Tabelle dargestellt werden.  
  
### Seitenzahl\-Informationen gespeichert CPrintInfo  
  
|Membervariablen oder<br /><br /> Funktionsname|Seitenzahl verwiesen|  
|--------------------------------------------|--------------------------|  
|`GetMinPage`\/`SetMinPage`|Die erste Seite des Dokuments|  
|`GetMaxPage`\/`SetMaxPage`|letzte Seite des Dokuments|  
|`GetFromPage`|Erste zu druckende Seite|  
|`GetToPage`|Gedruckt werden letzte Seite|  
|`m_nCurPage`|Seite, die aktuell gedruckt wird|  
  
 Seitennummern beginnen mit 1, d. h wird die erste Seite 1, nicht 0 nummeriert.  Weitere Informationen über diese und andere Member einer [CPrintInfo](../mfc/reference/cprintinfo-structure.md), finden Sie in der *MFC\-Referenz*.  
  
 am Anfang des Druckvorgangs ruft das Framework die [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)\-Memberfunktion der Ansicht auf und übergibt einen Zeiger auf eine Struktur. `CPrintInfo` Der Anwendungs\-Assistent stellt eine Implementierung von `OnPreparePrinting`, die [DoPreparePrinting](../Topic/CView::DoPreparePrinting.md) aufgerufen wird, eine andere Memberfunktion von `CView` bereit.  `DoPreparePrinting` ist die Funktion, die das Drucken dargestellt und einen Druckergerätekontext erstellt.  
  
 Zu diesem Zeitpunkt weiß die Anwendung nicht, wie viele Seiten im Dokument befinden.  Sie verwendet die Standardwerte 1 und 0xFFFF für die Anzahl der ersten und letzten Seite des Dokuments.  Wenn Sie wissen, wie viele Seiten das Dokument verfügt, überschreiben Sie `OnPreparePrinting` und Aufruf für [SetMaxPage](../Topic/CPrintInfo::SetMaxPage.md)`CPrintInfo` die Struktur, bevor Sie sie für `DoPreparePrinting` senden.  Dadurch können Sie die Länge des Dokuments angeben.  
  
 `DoPreparePrinting` zeigt dann das Dialogfeld Drucken an.  Wenn es beendet wird, enthält `CPrintInfo` die Struktur die Werte, die vom Benutzer angegeben werden.  Wenn der Benutzer nur einen ausgewählten Seitenbereich drucken möchte, kann er den an und Endseitenzahlen im Dialogfeld Drucken angeben.  Das Framework ruft diese Werte mithilfe der Funktionen `GetFromPage` und `GetToPage` von [CPrintInfo](../mfc/reference/cprintinfo-structure.md) ab.  Wenn der Benutzer keinen Seitenbereich angibt, ruft das Framework `GetMinPage` und `GetMaxPage` auf und verwendet die Werte, die zurückgegeben werden, um das gesamte Dokument zu drucken.  
  
 Für jede Seite eines zu druckende Dokument, ruft das Framework zwei Memberfunktionen bereit in der Ansichtsklasse, [OnPrepareDC](../Topic/CView::OnPrepareDC.md) und [OnPrint](../Topic/CView::OnPrint.md) auf und übergibt Parameter jeder Funktion zwei: ein Zeiger auf ein Objekt und [CDC](../mfc/reference/cdc-class.md) ein Zeiger auf eine Struktur. `CPrintInfo` Jedes Mal wenn das Framework `OnPrepareDC` und `OnPrint` aufgerufen wird, übergibt es einen anderen Wert im `m_nCurPage`\-Member `CPrintInfo` der Struktur.  Auf diese Weise weist das Framework der Ansicht mit, welcher Seite gedruckt werden soll.  
  
 Die Memberfunktion [OnPrepareDC](../Topic/CView::OnPrepareDC.md) wird auch für Bildschirmanzeige verwendet.  Sie nimmt Anpassungen den Gerätekontext vor, bevor das Zeichnen stattfindet.  `OnPrepareDC` dient eine ähnliche Rolle im Druck, es gibt jedoch ein paar Unterschiede: zuerst stellt das `CDC`\-Objekt einen Druckergerätekontext anstelle eines Bildschirm\-Gerätekontexts dar, und die zweite, wird ein `CPrintInfo`\-Objekt als zweiter Parameter übergeben. \(Dieser Parameter ist **NULL**, wenn `OnPrepareDC` für Bildschirmanzeige. aufgerufen wird\) Überschreiben Sie `OnPrepareDC`, um Anpassungen den Gerätekontext vorzunehmen, basierend auf der Seite auf.  Beispielsweise können Sie den Anzeigebereichsursprung und den Clippingbereich verschieben, um sicherzustellen, dass der entsprechende Teil des Dokuments gedruckt wird.  
  
 Die Memberfunktion [OnPrint](../Topic/CView::OnPrint.md) führt den eigentlichen Drucken der Seite aus.  Der Artikel [Wie Standard\-Druck ausgeführt wurde](../mfc/how-default-printing-is-done.md) zeigt, wie das Framework [OnDraw](../Topic/CView::OnDraw.md) mit einem Druckergerätekontext aufruft, um das Drucken auszuführen.  Genauer, die vom Framework aufgerufen wird `OnPrint` mit einer `CPrintInfo`\-Struktur und einem Gerätekontext und `OnPrint` übergibt der Gerätekontext zu `OnDraw`.  Überschreiben Sie `OnPrint`, um jedes Rendern auszuführen, das nur während des Drucks und nicht für Bildschirmanzeige ausgeführt werden soll.  Beispielsweise Kopf\- oder Fußzeilen drucken \(siehe den Artikel [Kopf\- und Fußzeilen](../mfc/headers-and-footers.md) weitere Informationen.\)  Anschließend rufen Sie `OnDraw` von der Überschreibung von `OnPrint`, dem der Renderingcommon die Bildschirmanzeige und zum Drucken verwendet.  
  
 Der Tatsache, dass `OnDraw` das Rendern für Bildschirmanzeige und Drucken wird, bedeutet, dass die Anwendung WYSIWYG\-Präsentation ist: "What You See Is What You Get". Aber Sie an, dass Sie keine WYSIWYG\-Anwendung schreiben.  Nehmen Sie einen Text\-Editor, der eine Fett Schriftart verwendet, um das Drucken Anzeigensteuerungscodes aber fett formatierten Text auf dem Bildschirm angeben.  In einer solchen Situation verwenden Sie `OnDraw` nur für Bildschirmanzeige.  Wenn Sie `OnPrint` überschreiben, ersetzen Sie den Aufruf von `OnDraw` durch einen Aufruf einer separaten Zeichnungsfunktion.  Diese Funktion das Dokument der Methode zeichnet, wird es auf Papier, mithilfe der Attribute, die Sie auf dem Bildschirm nicht angezeigt.  
  
##  <a name="_core_printer_pages_vs.._document_pages"></a> Drucker\-Seiten für Dokument\-Seiten  
 Wenn Sie die Seitenzahlen verweisen, zu unterscheiden ist gelegentlich unumgänglich, zwischen dem Konzept des Druckers einer Seite und dem Konzept des Dokuments eine Seite.  Hinsichtlich des Druckers ist eine Seite ein Blatt Papier.  Es entspricht ein Blatt Papier nicht notwendigerweise eine Seite des Dokuments.  Wenn Sie u drucken einen Newsletter, in dem die in gefaltet werden sollen, ein Blatt Papier jeweils ersten und letzten Seiten des Dokuments, nebeneinander enthalten.  Entsprechend beim Drucken eines Arbeitsblatts, besteht das Dokument keinen aus Seiten vorhanden.  Stattdessen kann ein Blatt Papier Zeilen 1 bis 20, die Spalten 6 bis 10.  
  
 Alle Seitenzahlen in der Struktur unter [CPrintInfo](../mfc/reference/cprintinfo-structure.md) finden Druckerseiten an.  Das Framework ruft `OnPrepareDC` und `OnPrint` jeweils für jedes Blatt Papier auf, das vom Drucker übergibt.  Wenn Sie die [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)\-Funktion überschreiben, um die Länge des Dokuments anzugeben, müssen Sie Druckerseiten verwenden.  Wenn eine 1:1\-Entsprechung, also gleich mit einen Druckerseiten eine dargestelltes Dokument\) enthält, dann ist dieser Vorgang unkompliziert.  Wenn hingegen Dokumentseiten und Druckerseiten nicht direkt entsprechen, müssen Sie sich zwischen diese übersetzen.  Beispielsweise sollten Sie, ein Arbeitsblatt zu drucken.  Wenn Sie `OnPreparePrinting` überschreiben, müssen Sie ableiten, wie viele Blätter Papier erforderlich sind, das gesamte Arbeitsblatt zu drucken und diesen Wert dann zu verwenden, wenn die `SetMaxPage`\-Memberfunktion von `CPrintInfo` aufrufen.  Auch wenn Sie `OnPrepareDC` überschreiben, müssen Sie `m_nCurPage` im Bereich von Zeilen und Spalten übersetzen, die auf diesem bestimmten Blatt werden und dann den Anzeigebereichsursprung entsprechend anpassen.  
  
##  <a name="_core_print.2d.time_pagination"></a> Die Druck\-Zeit\-Paginierung  
 In einigen Situationen weiß die Ansichtsklasse möglicherweise nicht im Voraus, wie lange das Dokument ist, bis sie wirklich gedruckt wurde.  Angenommen, dass nicht WYSIWYG\-Präsentation ist, das eine Länge des Dokuments auf dem Bildschirm nicht die Länge entspricht, falls gedruckt wird.  
  
 Dies verursacht ein Problem, wenn Sie [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) für die Ansichtsklasse überschreiben: Sie können keinen Wert in `SetMaxPage` der Funktion [CPrintInfo](../mfc/reference/cprintinfo-structure.md)\-Struktur übergeben, da Sie die Länge keins Dokuments kennen.  Wenn der Benutzer keine Seitenzahl angibt, um an der Anwendung des Druckdialogfeldfelds anzuhalten, weiß das Framework nicht, wann die Druckschleife beendet.  Die einzige Möglichkeit, zu bestimmen, wann die Druckschleife ist, das Dokument auszudrucken und finden beendet, bei.  die Ansichtsklasse muss für das Ende des Dokuments überprüfen, wie es gedruckt wird, und das Framework dann informieren, wenn das Ende erreicht wird.  
  
 Das Framework setzt auf [OnPrepareDC](../Topic/CView::OnPrepareDC.md)\-Funktion der Ansichtsklasse, um sie zu veranlassen, wann wird.  Nachdem jeder Aufruf von `OnPrepareDC`, dem Framework einen Member der Struktur `CPrintInfo` überprüft, die `m_bContinuePrinting` genannt wird.  Sein Standardwert ist **TRUE.** Solange er geringere bleibt, aktiviert das Framework die Druckschleife fort.  Wenn sie auf **FALSE** festgelegt wird, hält das Framework auf.  So DruckZeitpaginierung, `OnPrepareDC` überschreiben, um, ob das Ende des Dokuments und erreicht wurde, `m_bContinuePrinting` im Satz ausführen zu **FALSE** überprüft, wenn dies der Fall ist.  
  
 Die Standardimplementierung von `OnPrepareDC` wird `m_bContinuePrinting` auf **FALSE** fest, wenn die aktuelle Seite größer als 1. ist.  Dies bedeutet, dass, wenn die Länge des Dokuments nicht angegeben wurde, dem Framework wird, dass das Dokument eine Seite lang ist.  Dies hat zur Folge, dass Sie darauf achten müssen, wenn Sie die Basisklassenversion von `OnPrepareDC` aufrufen.  Nehmen Sie nicht an, dass `m_bContinuePrinting`**TRUE** ist, nachdem die Basisklassenversion aufgerufen hat.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Kopf\- und Fußzeilen](../mfc/headers-and-footers.md)  
  
-   [Zuordnen von GDI\-Ressourcen](../mfc/allocating-gdi-resources.md)  
  
## Siehe auch  
 [Drucken](../mfc/printing.md)   
 [CView Class](../mfc/reference/cview-class.md)   
 [CDC\-Klasse](../mfc/reference/cdc-class.md)