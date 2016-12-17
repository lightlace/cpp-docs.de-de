---
title: "In MFC verf&#252;gbare abgeleitete Ansichtsklassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], Abgeleitet"
  - "CView-Klasse, Klassen, die abgeleitet sind aus"
  - "Abgeleitete Klassen, Ansichtsklassen"
  - "Ansichtsklassen, Abgeleitet"
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# In MFC verf&#252;gbare abgeleitete Ansichtsklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgende Tabelle zeigt Ansichtsklassen und ihre Beziehungen zu MFC miteinander.  Die Funktionen der Ansichtsklasse hängen von der MFC\-Ansichtsklasse ab, von der sie abgeleitet.  
  
### Ansichtsklassen  
  
|Klasse|**Beschreibung**|  
|------------|----------------------|  
|[CView](../mfc/reference/cview-class.md)|Basisklasse aller Ansichten.|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Basisklasse von `CTreeView`, `CListView`, `CEditView` und `CRichEditView`.  Diese Klassen können Sie mit Dokument\-\/Ansichtarchitektur den angegebenen allgemeinen Windows\-Steuerelemente verwenden.|  
|[CEditView](../mfc/reference/ceditview-class.md)|Eine einfache Ansicht auf Grundlage des Windows\-Eingabefeldsteuerelement.  Ermöglicht das Hinzufügen und Bearbeiten von Text und als Grundlage für eine einfache Texteditor\-Anwendung verwendet werden.  Siehe auch `CRichEditView`.|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Eine Ansicht, die eine [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\-Objekt enthält.  Diese Klasse ist `CEditView`, ist jedoch im Gegensatz zu `CEditView`, `CRichEditView` Handleformatierter text analog.|  
|[CListView](../mfc/reference/clistview-class.md)|Eine Ansicht, die eine [Verwendung](../mfc/reference/clistctrl-class.md)\-Objekt enthält.|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|Eine Ansicht, die eine [CTreeCtrl](../mfc/reference/ctreectrl-class.md)\-Objekt, für Ansichten enthält, die im Fenster "Projektmappen\-Explorer" in Visual C\+\+ ähneln.|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|Basisklasse von `CFormView`, `CRecordView` und `CDaoRecordView`.  Implementiert, die den Inhalt der Ansicht wechseln.|  
|[CFormView](../mfc/reference/cformview-class.md)|Eine Formularansicht, eine Ansicht, die Steuerelemente enthalten.  Eine formularbasierte Anwendung stellt eine oder mehrere solcher Formularschnittstellen.|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Eine Webbrowseransicht, mit der der Benutzer der Anwendung Websites im World Wide Web suchen kann und Ordner im lokalen Dateisystem und im Netzwerk.  Die Webbrowseransicht kann als Active Document\-Container auch arbeiten.|  
|[CRecordView](../mfc/reference/crecordview-class.md)|Eine Formularansicht, die ODBC\-Datenbanksätze in Steuerelementen anzeigt.  Wenn Sie ODBC\-Unterstützung im Projekt auswählen, ist die Basisklasse der Ansicht `CRecordView`.  Die Ansicht wird mit einem `CRowset`\-Objekt verbunden.|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Eine Formularansicht, die DAO\-Datenbank\-Datenbanksätze in Steuerelementen anzeigt.  Wenn Sie DAO\-Unterstützung im Projekt auswählen, ist die Basisklasse der Ansicht `CDaoRecordView`.  Die Ansicht wird mit einem `CDaoRecordset`\-Objekt verbunden.|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|Eine Formularansicht, die OLE DB\-Datensätze in Steuerelementen anzeigt.  Wenn Sie OLE DB\-Unterstützung im Projekt auswählen, ist die Basisklasse der Ansicht `COleDBRecordView`.  Die Ansicht wird mit einem `CRowset`\-Objekt verbunden.|  
  
> [!NOTE]
>  Seit MFC 4.0, wird `CEditView` von `CCtrlView` abgeleitet.  
  
 Um diese Klassen in der Anwendung zu verwenden, leiten Sie die Ansichtsklassen der Anwendung von diesen.  Weitere Informationen finden Sie unter [Bildlauf\- und Skalierungs\-Ansichten](../mfc/scrolling-and-scaling-views.md).  Weitere Informationen über die Datenbankklassen, finden Sie unter [Übersicht: Datenbank\-Programmierung](../data/data-access-programming-mfc-atl.md).  
  
## Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)