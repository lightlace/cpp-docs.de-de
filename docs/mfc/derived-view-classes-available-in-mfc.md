---
title: In MFC verfügbare abgeleitete Ansichtsklassen
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 9972586bd0cc4059e81d81be954a8cf0cada1f0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594496"
---
# <a name="derived-view-classes-available-in-mfc"></a>In MFC verfügbare abgeleitete Ansichtsklassen

Die folgende Tabelle zeigt die MFC Klassen und deren Beziehungen untereinander. Die Funktionen der Ansichtsklasse, abhängig von der MFC-Ansicht-Klasse, die von der er abgeleitet.

### <a name="view-classes"></a>Ansichtsklassen

|Klasse|Beschreibung|
|-----------|-----------------|
|[CView](../mfc/reference/cview-class.md)|Basisklasse für alle Ansichten.|
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Die Basisklasse des `CTreeView`, `CListView`, `CEditView`, und `CRichEditView`. Diese Klassen können Sie die Dokument-/Ansichtarchitektur mit die angegebenen Windows-Standardsteuerelemente verwenden.|
|[CEditView](../mfc/reference/ceditview-class.md)|Eine einfache Ansicht basierend auf dem Windows bearbeiten-Steuerelement. Ermöglicht das eingeben und Bearbeiten von Text und können als Grundlage für einen einfachen Text-Editor-Anwendung verwendet werden. Siehe auch `CRichEditView`.|
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Eine Ansicht mit einem [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) Objekt. Diese Klasse ist analog zu `CEditView`, aber im Gegensatz zum `CEditView`, `CRichEditView` Handles von formatiertem Text.|
|[CListView](../mfc/reference/clistview-class.md)|Eine Ansicht mit einem [CListCtrl](../mfc/reference/clistctrl-class.md) Objekt.|
|[CTreeView](../mfc/reference/ctreeview-class.md)|Eine Ansicht mit einem [CTreeCtrl](../mfc/reference/ctreectrl-class.md) -Objekt, um Sichten, die die Projektmappen-Explorer-Fenster in Visual C++ entsprechen.|
|[CScrollView](../mfc/reference/cscrollview-class.md)|Die Basisklasse des `CFormView`, `CRecordView`, und `CDaoRecordView`. Implementiert den Inhalt der Ansicht zu scrollen.|
|[CFormView](../mfc/reference/cformview-class.md)|Eine Formularansicht und eine Ansicht, die Steuerelemente enthält. Eine formularbasierte Anwendung enthält eine oder mehrere solche Form Schnittstellen.|
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Eine Web-Browser-Ansicht mit der Benutzer der Anwendung, Websites auf der World Wide Web sowie die Ordner im lokalen Dateisystem und in einem Netzwerk suchen kann. Die Webbrowseransicht kann auch als Active Document-Container funktionieren.|
|[CRecordView](../mfc/reference/crecordview-class.md)|Eine Formularansicht, die ODBC-Datenbankdatensätze in Steuerelementen anzeigt. Wenn Sie ODBC-Unterstützung in Ihrem Projekt auswählen, ist die Basisklasse der Ansicht `CRecordView`. Die Ansicht verbunden ist, um eine `CRowset` Objekt.|
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Eine Formularansicht die DAO-Datenbankdatensätze in Steuerelementen anzeigt. Wenn Sie die DAO-Unterstützung in Ihrem Projekt auswählen, ist die Basisklasse der Ansicht `CDaoRecordView`. Die Ansicht verbunden ist, um eine `CDaoRecordset` Objekt.|
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|Eine Formularansicht die OLE DB-Datensätze in Steuerelementen anzeigt. Wenn Sie OLE DB-Unterstützung in Ihrem Projekt auswählen, ist die Basisklasse der Ansicht `COleDBRecordView`. Die Ansicht verbunden ist, um eine `CRowset` Objekt.|

> [!NOTE]
>  Ab MFC 4.0 `CEditView` ergibt sich aus `CCtrlView`.

Um diese Klassen in Ihrer Anwendung verwenden zu können, werden leiten Sie der Anwendung Klassen von ihnen ab. Weitere Informationen finden Sie unter [Bildlauf und Skalierung von Ansichten](../mfc/scrolling-and-scaling-views.md). Weitere Informationen zu den Datenbankklassen, finden Sie unter [Overview: Programmieren von Datenbank](../data/data-access-programming-mfc-atl.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von Ansichten](../mfc/using-views.md)

