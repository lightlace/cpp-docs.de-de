---
title: Anzeigen von Klassen (Windows) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.view
dev_langs: C++
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0148ead7a978389f763efbe9ee6306ec7a5839cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="view-classes-windows"></a>Ansichtsklassen (Windows)
`CView`und die abgeleiteten Klassen sind untergeordnete Fenster, die den Clientbereich eines Rahmenfensters darstellen. Ansichten anzeigen von Daten und Eingaben für ein Dokument.  
  
 View-Klasse, die einer Dokumentklasse und einem Rahmenfenster (Klasse) mit einem Dokument Template-Objekt zugeordnet ist.  
  
 [CView](../mfc/reference/cview-class.md)  
 Die Basisklasse für eine anwendungsspezifische Ansicht der Daten eines Dokuments. Ansichten anzeigen von Daten und Benutzereingaben zum Bearbeiten, oder wählen Sie die Daten akzeptieren. Leiten Sie Ihre Ansichtsklasse oder Klassen von `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 Die Basisklasse für Ansichten mit Bildlauffunktionen. Leiten Sie Ihre Ansichtsklasse aus `CScrollView` für den automatischen Bildlauf.  
  
## <a name="form-and-record-views"></a>Formular und Datensatzansichten  
 Formularansichten sind auch Sichten Durchführen eines Bildlaufs. Sie basieren auf einer Dialogfeldvorlage.  
  
 Formularansichten sind Datensatzansichten abgeleitet. Zusätzlich zu der Dialogfeldvorlage verfügen über eine Verbindung mit einer Datenbank.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Eine Scroll-Sicht, deren Layout in einer Dialogfeldvorlage definiert ist. Leiten Sie eine Klasse von `CFormView` eine Benutzeroberfläche, die basierend auf einer Dialogfeldvorlage implementieren.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Stellt eine Form anzeigen, die direkt mit einem Recordset-Objekt (Datenzugriffsobjekt) verbunden. Alle Formularansichten, wie eine `CDaoRecordView` basiert auf einer Dialogfeldvorlage.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Stellt eine Form anzeigen, die direkt mit einer Open Database Connectivity (ODBC)-Recordset-Objekt verbunden. Alle Formularansichten, wie eine `CRecordView` basiert auf einer Dialogfeldvorlage.  
  
 [CHtmlEditView](../mfc/reference/chtmleditview-class.md)  
 Eine Formularansicht, die die Funktionalität der WebBrowser HTML-Bearbeitung Plattform bereitstellt.  
  
## <a name="control-views"></a>Steuerelementansicht  
 Steuerelementansicht Anzeigen eines Steuerelements als eigene Ansicht.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Die Basisklasse für alle Ansichten, die Windows-Steuerelementen zugeordnet. Die Ansichten, die basierend auf Steuerelemente werden nachfolgend beschrieben.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Bearbeitungssteuerelement für eine Sicht, einen Windows-Standard enthält (siehe [CEdit](../mfc/reference/cedit-class.md)). Bearbeiten Sie die Steuerelemente unterstützen Textbearbeitung, suchen, ersetzen und Bildlauffunktionen.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Eine Sicht, enthält eine umfangreiche Windows-Bearbeitungssteuerelements (finden Sie unter [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Zusätzlich zu den Funktionen eines Bearbeitungssteuerelements bearbeiten Rich Steuerelemente Unterstützung Schriftarten, Farben, absatzformatierung und eingebetteten OLE-Objekten.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Eine Sicht, ein Windows-Listensteuerelement enthält (siehe [CListCtrl](../mfc/reference/clistctrl-class.md)). Ein Listenfeld-Steuerelement zeigt eine Auflistung von Elementen in der jedes ein Symbol und eine Bezeichnung, ähnlich wie in den rechten Bereich des Datei-Explorer besteht.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Eine Sicht, ein Windows-Strukturansicht-Steuerelement enthält (siehe [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Ein Strukturansicht-Steuerelement zeigt eine hierarchische Liste der Symbole und Bezeichnungen auf ähnliche Weise im linken Bereich des Datei-Explorers auf bestimmte Weise angeordnet.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 `CSplitterWnd`können Sie mehrere Ansichten in einem einzelnen Rahmenfenster haben. `CPrintDialog`und `CPrintInfo` Unterstützung für das Drucken und Druckvorschau Ansichten. `CRichEditDoc`und `CRichEditCntrItem` werden zusammen mit `CRichEditView` OLE-Container-Funktionen zu implementieren.  
  
 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)  
 Ein Fenster, das der Benutzer in mehrere Bereiche aufgeteilt werden kann. Diese Bereiche können durch den Benutzer oder eine feste Größe geändert werden.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Stellt ein Standarddialogfeld zum Drucken einer Datei an.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 Eine Struktur, die Informationen zu einem Auftrag Druckauftrags oder seitenansichtauftrags enthält. Verwendet von `CView`Architektur des drucken.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Verwaltet die Liste der OLE-Client-Elemente, die in einem `CRichEditView`.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Ermöglicht die clientseitige Zugriff auf ein Element in gespeicherten OLE eine `CRichEditView`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

