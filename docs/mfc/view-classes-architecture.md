---
title: Anzeigen von Klassen (Architektur) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.view
dev_langs:
- C++
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11bb3d9e551089a156d255f7b27fb55cbe87bdbe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383746"
---
# <a name="view-classes-architecture"></a>Ansichtsklassen (Architektur)
`CView` und die abgeleiteten Klassen sind untergeordnete Fenster, die den Clientbereich eines Rahmenfensters darstellen. Ansichten anzeigen von Daten und Eingaben für ein Dokument.  
  
 View-Klasse, die einer Dokumentklasse und einem Rahmenfenster (Klasse) mit einem Dokument Template-Objekt zugeordnet ist.  
  
 [CView](../mfc/reference/cview-class.md)  
 Die Basisklasse für eine anwendungsspezifische Ansicht der Daten eines Dokuments. Ansichten anzeigen von Daten und Benutzereingaben zum Bearbeiten, oder wählen Sie die Daten akzeptieren. Leiten Sie Ihre Ansicht Klasse(n) aus `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 Die Basisklasse für Ansichten mit Bildlauffunktionen. Leiten Sie Ihre Ansichtsklasse aus `CScrollView` für den automatischen Bildlauf.  
  
## <a name="form-and-record-views"></a>Formular und Datensatzansichten  
 Formularansichten sind auch Sichten Durchführen eines Bildlaufs. Sie basieren auf einer Dialogfeldvorlage.  
  
 Formularansichten sind Datensatzansichten abgeleitet. Zusätzlich zu der Dialogfeldvorlage verfügen über eine Verbindung mit einer Datenbank.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Eine Scroll-Sicht, deren Layout in einer Dialogfeldvorlage definiert ist. Leiten Sie eine Klasse von `CFormView` eine Benutzeroberfläche, die basierend auf einer Dialogfeldvorlage implementieren.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Stellt eine Form anzeigen, die direkt mit einem Recordset-Objekt (Datenzugriffsobjekt) verbunden. Alle Formularansichten, wie eine `CDaoRecordView` basiert auf einer Dialogfeldvorlage.  
  
 [CHtmlView](../mfc/reference/chtmlview-class.md)  
 Unterstützt ein Steuerelement für Webbrowser innerhalb einer Anwendung. Das Steuerelement unterstützt dynamische HTML in MFC.  
  
 [COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)  
 Bietet MFC-OLE DB-Unterstützung für Formularansichten.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Stellt eine Form anzeigen, die direkt mit einer Open Database Connectivity (ODBC)-Recordset-Objekt verbunden. Alle Formularansichten, wie eine `CRecordView` basiert auf einer Dialogfeldvorlage.  
  
## <a name="control-views"></a>Steuerelementansicht  
 Steuerelementansicht Anzeigen eines Steuerelements als eigene Ansicht.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Die Basisklasse für alle Ansichten, die Windows-Steuerelementen zugeordnet. Die Ansichten, die basierend auf Steuerelemente werden nachfolgend beschrieben.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Bearbeitungssteuerelement für eine Sicht, einen Windows-Standard enthält (siehe [CEdit](../mfc/reference/cedit-class.md)). Bearbeiten Sie die Steuerelemente unterstützen Textbearbeitung, suchen, ersetzen und Bildlauffunktionen.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Eine Sicht, enthält eine umfangreiche Windows-Bearbeitungssteuerelements (finden Sie unter [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Zusätzlich zu den Funktionen eines Bearbeitungssteuerelements bearbeiten Rich Steuerelemente Unterstützung Schriftarten, Farben, absatzformatierung und eingebetteten OLE-Objekten.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Eine Sicht, ein Windows-Listensteuerelement enthält (siehe [CListCtrl](../mfc/reference/clistctrl-class.md)). Ein Listenfeld-Steuerelement zeigt die Symbole und Zeichenfolgen ähnlich wie in den rechten Bereich des Datei-Explorer.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Eine Sicht, ein Windows-Strukturansicht-Steuerelement enthält (siehe [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Ein Strukturansicht-Steuerelement zeigt Symbole und Zeichenfolgen, die in einer Hierarchie auf ähnliche Weise in den linken Bereich des Datei-Explorers angeordnet sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

