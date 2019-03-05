---
title: Ansichtsklassen (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
ms.openlocfilehash: ad58fd6fa2548c2cf320baf75b8fc33a835ddd55
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267094"
---
# <a name="view-classes-windows"></a>Ansichtsklassen (Windows)

`CView` und die abgeleiteten Klassen sind untergeordnete Fenster, die darstellen, das den Clientbereich eines Rahmenfensters. Ansichten Daten anzeigen und akzeptieren eine Eingabe für ein Dokument.

Eine Ansichtsklasse ist mit einer Dokumentklasse und einem Rahmenfenster (Klasse) mit einem Dokumentvorlagen-Objekt zugeordnet.

[CView](../mfc/reference/cview-class.md)<br/>
Die Basisklasse für anwendungsspezifische Sichten der Daten eines Dokuments. Ansichten anzeigen von Daten und Benutzereingaben, um zu bearbeiten, oder wählen Sie die Daten akzeptieren. Leiten Sie Ihre Ansichtsklasse oder Klassen von `CView`.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Die Basisklasse für Ansichten mit Bildlauffunktionen. Ableiten der Klasse "View" aus `CScrollView` für den automatischen Bildlauf.

## <a name="form-and-record-views"></a>Formular und Datensatzansichten

Formularansichten sind auch Ansichten Bildlauf. Sie basiert auf einer Dialogfeldvorlage.

Datensatzansichten werden von Formularansichten abgeleitet. Zusätzlich zu der Dialogfeldvorlage haben sie auch eine Verbindung mit einer Datenbank.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Eine Bildlaufansicht, deren Layout in eine Dialogfeldvorlage definiert ist. Leiten Sie eine Klasse von `CFormView` zur Implementierung einer Benutzeroberfläche, die basierend auf einer Dialogfeldvorlage.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Stellt eine Form anzeigen, die direkt mit einem Recordset-Objekt (Data Access Object, DAO) verbunden. Alle Formularansichten, wie eine `CDaoRecordView` basiert auf einer Dialogfeldvorlage.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Stellt eine Form anzeigen, die direkt mit einer Open Database Connectivity (ODBC)-Recordset-Objekt verbunden. Alle Formularansichten, wie eine `CRecordView` basiert auf einer Dialogfeldvorlage.

[CHtmlEditView](../mfc/reference/chtmleditview-class.md)<br/>
Eine Formularansicht, die die Funktionalität der WebBrowser HTML-Bearbeitung Plattform bereitstellt.

## <a name="control-views"></a>Steuerelementansicht

Steuerelementansicht Steuerelement, die als ihre Ansicht angezeigt wird.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Die Basisklasse für alle Ansichten, die Windows-Steuerelementen zugeordnet. Die Ansichten, die basierend auf werden nachfolgend beschrieben.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Bearbeitungssteuerelement für eine Sicht, einen Windows-Standard enthält (siehe [CEdit](../mfc/reference/cedit-class.md)). Bearbeiten Sie die Steuerelemente unterstützen Text-Bearbeitung, suchen, ersetzen und Bildlauffunktionen.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Eine Ansicht, enthält eine umfassende Windows-Bearbeitungssteuerelement (finden Sie unter [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Zusätzlich zu den Funktionen eines Steuerelements bearbeiten Bearbeiten umfangreiche Steuerelemente unterstützen Schriftarten, Farben, absatzformatierung und eingebettete OLE-Objekte.

[CListView](../mfc/reference/clistview-class.md)<br/>
Eine Sicht, ein Windows-Steuerelement enthält (siehe [CListCtrl](../mfc/reference/clistctrl-class.md)). Ein Listensteuerelement zeigt eine Auflistung von Elementen, jedes ein Symbol und eine Bezeichnung, ähnlich wie in den rechten Bereich des Datei-Explorers aus.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Eine Sicht, ein Windows-Strukturansicht-Steuerelement enthält (siehe [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Ein Strukturansicht-Steuerelement zeigt eine hierarchische Liste der Symbole und Bezeichnungen, die auf ähnliche Weise im linken Bereich des Datei-Explorers auf bestimmte Weise angeordnet.

## <a name="related-classes"></a>Verwandte Klassen

`CSplitterWnd` können Sie mehrere Sichten enthalten, in einem einzelnen Rahmenfenster. `CPrintDialog` und `CPrintInfo` Unterstützung für das Drucken und Druckvorschau der Ansichten. `CRichEditDoc` und `CRichEditCntrItem` dienen mit `CRichEditView` OLE-Container-Funktionen zu implementieren.

[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)<br/>
Ein Fenster, die der Benutzer in mehrere Bereiche aufteilen können. Diese Bereiche möglich mit veränderbarer Größe durch den Benutzer oder eine feste Größe.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Stellt ein Standarddialogfeld zum Drucken einer Datei bereit.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
Eine Struktur, die Informationen zu einem Auftrag des Druckauftrags oder seitenansichtauftrags enthält. Ein, die `CView`die Druck-Architektur.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Verwaltet die Liste der OLE-Client-Elemente, die in einem `CRichEditView`.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
Bietet eine clientseitige-Zugriff auf ein Element in gespeicherten OLE eine `CRichEditView`.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
