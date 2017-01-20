---
title: "Ansichtsklassen (Architektur)"
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
  - "Steuerelementansicht"
  - "Form- und Datensatzansichten"
  - "Ansichtsklassen"
  - "Ansichtsklassen, Architektur"
ms.assetid: 8894579a-1436-441e-b985-83711061e495
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ansichtsklassen (Architektur)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CView` und abgeleitete Klassen sind untergeordnete Fenster, die den Innenbereich eines Rahmenfensters darstellen.  Ansichten zeigen Daten an und akzeptieren Eingabe für ein Dokument.  
  
 Eine Ansichtsklasse wird mit einer Dokumentklasse und einer Rahmenfensterklasse mithilfe eines Dokumentvorlagenobjekts zugeordnet.  
  
 [CView](../mfc/reference/cview-class.md)  
 Die Basisklasse für anwendungsspezifische Ansichten der Daten eines Dokuments.  Ansichtsanzeigendaten und akzeptieren Benutzereingaben, um die Daten zu bearbeiten oder auszuwählen.  Leiten Sie die Ansichtsklasse von `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 Die Basisklasse für Ansichten mit Bildlauffunktionen.  Leiten Sie die Ansichtsklasse von `CScrollView` für automatischen Bildlaufs.  
  
## Formular und Datensatzansichten  
 Formularansichten führen außerdem Ansichten durch.  Sie sind auf einer Dialogfeldvorlage.  
  
 Datensatzansichten werden von den Formularansichten abgeleitet.  Neben der Dialogfeldvorlage haben sie auch eine Verbindung mit einer Datenbank.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Eine Bildlaufansicht, deren Layout in einer Dialogfeldvorlage definiert wird.  Leiten Sie eine Klasse von `CFormView`, um eine Benutzeroberfläche auf einer Dialogfeldvorlage zu implementieren.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Stellt eine Formularansicht bereit, die direkt an ein Datenzugriffsobjekt \(dao\)\- Recordset\-Objekt verbunden ist.  Wie alle Formularansichten ist `CDaoRecordView` auf einer Dialogfeldvorlage.  
  
 [CHtmlView](../mfc/reference/chtmlview-class.md)  
 Unterstützt ein Steuerelement für Webbrowsen innerhalb einer Anwendung.  Das Steuerelement unterstützt Dynamic HTML in MFC.  
  
 [COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)  
 Bietet MFC\-OLEDB\-Unterstützung für Formularansichten.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Stellt eine Formularansicht bereit, die direkt mit einem Recordset\-Objekt verbunden wird der Open Database Connectivity \(ODBC\).  Wie alle Formularansichten ist `CRecordView` auf einer Dialogfeldvorlage.  
  
## Steuerelementansichten  
 Steuerelementansichten werden ein Steuerelement als ihre Ansicht.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Alle Basisklasse für zeigt zugeordnet Windows\-Steuerelementen an.  Die Ansichten auf Basis von Steuerelementen sind unten beschrieben.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Eine Ansicht, die ein Windows\-Standardbearbeitungssteuerelement enthält \(siehe [CEdit](../mfc/reference/cedit-class.md)\).  Bearbeitungssteuerelementstütztextausgabe, Funktionen, suchend ersetzen, und wechseln.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Eine Ansicht, die ein Windows\-Rich\-Edit\-Steuerelement enthält \(siehe [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\).  Neben den Funktionen eines Bearbeitungssteuerelements, unterstützen derzeit Schriftarten, Farben, und Absatzformatierung eingebettete OLE\-Objekte.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Eine Ansicht, die ein Windows\-Listensteuerelement enthält \(siehe [Verwendung](../mfc/reference/clistctrl-class.md)\).  Ein Listensteuerelement sind die Symbole und Zeichenfolgen an, die dem rechten Bereich des Datei\-Explorers fast genauso sind.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Eine Ansicht, die ein Windows\-Strukturansicht\-Steuerelement enthält \(siehe [CTreeCtrl](../mfc/reference/ctreectrl-class.md)\).  Eine Strukturansicht sind die Symbole und Zeichenfolgen an, die in einer Hierarchie angeordnet, die in den linken Bereich des Datei\-Explorers fast genauso ist.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)