---
title: "Abgeleitete Ansichtsklassen in MFC verfügbare | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2426f3e547da6eaab6a4b38bb5199e87c93ef933
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="derived-view-classes-available-in-mfc"></a>In MFC verfügbare abgeleitete Ansichtsklassen
Die folgende Tabelle zeigt die Klassen von MFC Ansicht und deren Beziehungen untereinander. Die Funktionen der Ansichtsklasse hängen von der MFC-View-Klasse, die von der er abgeleitet wird.  
  
### <a name="view-classes"></a>Ansichtsklassen  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[CView](../mfc/reference/cview-class.md)|Die Basisklasse aller Ansichten.|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Basisklasse des `CTreeView`, `CListView`, `CEditView`, und `CRichEditView`. Diese Klassen können Sie die Dokument-/Ansichtarchitektur mit der angegebenen Windows-Standardsteuerelemente verwenden.|  
|[CEditView](../mfc/reference/ceditview-class.md)|Eine einfache Sicht, die von der Windows-basierten bearbeiten-Steuerelement. Ermöglicht das eingeben und Bearbeiten von Text und kann als Grundlage für einen einfachen Text-Editor-Anwendung verwendet werden. Siehe auch `CRichEditView`.|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Eine Sicht mit einem [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) Objekt. Diese Klasse ist analog zu `CEditView`, aber im Gegensatz zum `CEditView`, `CRichEditView` Handles formatierten Text.|  
|[CListView](../mfc/reference/clistview-class.md)|Eine Sicht mit einem [CListCtrl](../mfc/reference/clistctrl-class.md) Objekt.|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|Eine Sicht mit einem [CTreeCtrl](../mfc/reference/ctreectrl-class.md) -Objekt, um Sichten, die das Fenster Projektmappen-Explorer in Visual C++ ähneln.|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|Basisklasse des `CFormView`, `CRecordView`, und `CDaoRecordView`. Implementiert einen Bildlauf der Ansicht Inhalt.|  
|[CFormView](../mfc/reference/cformview-class.md)|Eine Formularansicht, eine Sicht, die Steuerelemente enthält. Eine formularbasierte Anwendung stellt eine oder mehrere solche Formular Schnittstellen bereit.|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Eine Webbrowseransicht, mit dem Benutzer der Anwendung Websites die World Wide Web sowie die Ordner im lokalen Dateisystem und in einem Netzwerk navigieren kann. Die Webbrowseransicht kann auch als Active Document-Container arbeiten.|  
|[CRecordView](../mfc/reference/crecordview-class.md)|Eine Formularansicht, die ODBC-Datenbankdatensätze in Steuerelementen anzeigt. Bei Auswahl von ODBC-Unterstützung in Ihrem Projekt wird die Sicht Basisklasse `CRecordView`. Die Ansicht mit verbunden ist ein `CRowset` Objekt.|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Eine Formularansicht die DAO-Datenbankdatensätze in Steuerelementen anzeigt. Bei Auswahl von DAO-Unterstützung in Ihrem Projekt wird die Sicht Basisklasse `CDaoRecordView`. Die Ansicht mit verbunden ist ein `CDaoRecordset` Objekt.|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|Eine Formularansicht, die OLE DB-Datensätze in Steuerelementen anzeigt. Bei Auswahl von OLE DB-Unterstützung in Ihrem Projekt wird die Sicht Basisklasse `COleDBRecordView`. Die Ansicht mit verbunden ist ein `CRowset` Objekt.|  
  
> [!NOTE]
>  Ab MFC 4.0 `CEditView` stammt aus `CCtrlView`.  
  
 Zum Verwenden dieser Klassen in der Anwendung werden Sie Ansichtsklassen für die Anwendung, die von ihnen abgeleitet. Weitere Informationen finden Sie unter [Bildlauf und Skalierung von Ansichten](../mfc/scrolling-and-scaling-views.md). Weitere Informationen zu den Datenbankklassen, finden Sie unter [(Übersicht): Datenbank-Programmierung](../data/data-access-programming-mfc-atl.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)

