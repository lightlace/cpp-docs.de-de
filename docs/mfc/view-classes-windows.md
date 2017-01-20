---
title: "Ansichtsklassen (Windows)"
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
  - "vc.classes.view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Form- und Datensatzansichten"
  - "Splitterfenster-Klassen"
  - "Ansichtsklassen, Windows"
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ansichtsklassen (Windows)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CView` und abgeleitete Klassen sind untergeordnete Fenster, die den Innenbereich eines Rahmenfensters darstellen.  Ansichten zeigen Daten an und akzeptieren Eingabe für ein Dokument.  
  
 Eine Ansichtsklasse wird mit einer Dokumentklasse und einer Rahmenfensterklasse mithilfe eines Dokumentvorlagenobjekts zugeordnet.  
  
 [CView](../mfc/reference/cview-class.md)  
 Die Basisklasse für anwendungsspezifische Ansichten der Daten eines Dokuments.  Ansichtsanzeigendaten und akzeptieren Benutzereingaben, um die Daten zu bearbeiten oder auszuwählen.  Leiten Sie die Ansichtsklasse oder Klassen von `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 Die Basisklasse für Ansichten mit Bildlauffunktionen.  Leiten Sie die Ansichtsklasse von `CScrollView` für automatischen Bildlaufs.  
  
## Formular und Datensatzansichten  
 Formularansichten führen außerdem Ansichten durch.  Sie sind auf einer Dialogfeldvorlage.  
  
 Datensatzansichten werden von den Formularansichten abgeleitet.  Neben der Dialogfeldvorlage haben sie auch eine Verbindung mit einer Datenbank.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Eine Bildlaufansicht, deren Layout in einer Dialogfeldvorlage definiert wird.  Leiten Sie eine Klasse von `CFormView`, um eine Benutzeroberfläche auf einer Dialogfeldvorlage zu implementieren.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Stellt eine Formularansicht bereit, die direkt an ein Datenzugriffsobjekt \(dao\)\- Recordset\-Objekt verbunden ist.  Wie alle Formularansichten ist `CDaoRecordView` auf einer Dialogfeldvorlage.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Stellt eine Formularansicht bereit, die direkt mit einem Recordset\-Objekt verbunden wird der Open Database Connectivity \(ODBC\).  Wie alle Formularansichten ist `CRecordView` auf einer Dialogfeldvorlage.  
  
 [CHtmlEditView](../mfc/reference/chtmleditview-class.md)  
 Eine Formularansicht, die die Funktionalität der Bearbeitungsplattform des web browser HTML enthält.  
  
## Steuerelementansichten  
 Steuerelementansichten werden ein Steuerelement als ihre Ansicht.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Alle Basisklasse für zeigt zugeordnet Windows\-Steuerelementen an.  Die Ansichten auf Basis von Steuerelementen sind unten beschrieben.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Eine Ansicht, die ein Windows\-Standardbearbeitungssteuerelement enthält \(siehe [CEdit](../mfc/reference/cedit-class.md)\).  Bearbeitungssteuerelementstütztextausgabe, Funktionen, suchend ersetzen, und wechseln.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Eine Ansicht, die ein Windows\-Rich\-Edit\-Steuerelement enthält \(siehe [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\).  Neben den Funktionen eines Bearbeitungssteuerelements, unterstützen derzeit Schriftarten, Farben, und Absatzformatierung eingebettete OLE\-Objekte.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Eine Ansicht, die ein Windows\-Listensteuerelement enthält \(siehe [Verwendung](../mfc/reference/clistctrl-class.md)\).  Ein Listensteuerelement zeigt eine Auflistung von Elementen, jede an, die einem Symbol und einer Bezeichnung, besteht fast genauso den rechten Bereich des Datei\-Explorers.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Eine Ansicht, die ein Windows\-Strukturansicht\-Steuerelement enthält \(siehe [CTreeCtrl](../mfc/reference/ctreectrl-class.md)\).  Eine Strukturansicht zeigt eine hierarchische Liste von Symbolen und von Bezeichnungen angeordnetem in ähnlicher Weise ähnlichem in den linken Bereich des Datei\-Explorers an.  
  
## Verwandte Klassen  
 `CSplitterWnd` ermöglicht es Ihnen, innerhalb mehrere Ansichten eines einzelnen Rahmenfensters verfügen.  `CPrintDialog` und `CPrintInfo` unterstützen die Drucks\- und Seitenansichtsfähigkeit von Ansichten.  `CRichEditDoc` und `CRichEditCntrItem` werden zusammen mit `CRichEditView` verwendet, um OLE\-Containerfunktionen zu implementieren.  
  
 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)  
 Ein Fenster, das der Benutzer in mehrere Bereiche aufteilen kann.  Diese Bereiche können vom Benutzer oder die korrigierte Größe veränderbar sein.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Stellt ein Standarddialogfeld zum Drucken einer Datei.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 Eine Struktur, die Informationen über einen Drucks\- oder Seitenansichtsauftrag enthält.  Wird von `CView`, das gedruckt Architektur.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Führt die Liste der OLE\-Clientelementen, die in `CRichEditView`.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Bietet clientseitigen Zugriff auf ein OLE\-Element, das im `CRichEditView` gespeichert wird.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)