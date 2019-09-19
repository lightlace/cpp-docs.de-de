---
title: Ansichtsklassen (Windows)
ms.date: 09/17/2019
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
ms.openlocfilehash: f3e9ea2ebf3eb0ce04fde0339aaf0243686248a9
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096045"
---
# <a name="view-classes-windows"></a>Ansichtsklassen (Windows)

`CView`und die abgeleiteten Klassen sind untergeordnete Fenster, die den Client Bereich eines Rahmen Fensters darstellen. Sichten zeigen Daten an und akzeptieren Eingaben für ein Dokument.

Eine Ansichts Klasse wird mithilfe eines Document-Template-Objekts einer Dokument Klasse und einer Rahmen Fenster Klasse zugeordnet.

[CView](../mfc/reference/cview-class.md)<br/>
Die Basisklasse für anwendungsspezifische Ansichten der Daten eines Dokuments. Sichten zeigen Daten an und akzeptieren Benutzereingaben, um die Daten zu bearbeiten oder auszuwählen. Leiten Sie die Ansichts Klasse oder `CView`die Klassen von ab.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Die Basisklasse für Ansichten mit scrollfunktionen. Leiten Sie Ihre Ansichts `CScrollView` Klasse von für den automatischen Bildlauf ab.

## <a name="form-and-record-views"></a>Formular-und Daten Satz Sichten

Formular Ansichten sind auch scrollansichten. Sie basieren auf einer Dialogfeld Vorlage.

Daten Satz Sichten werden von Formular Ansichten abgeleitet. Zusätzlich zu der Dialogfeld Vorlage haben Sie auch eine Verbindung mit einer-Datenbank.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Eine scrollansicht, deren Layout in einer Dialogfeld Vorlage definiert ist. Leiten Sie eine Klasse `CFormView` von ab, um eine Benutzeroberfläche zu implementieren, die auf einer Dialogfeld Vorlage basiert.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Stellt eine Formularansicht bereit, die direkt mit einem DAO-Recordset-Objekt (Data Access Object) verbunden ist. Wie alle Formular Ansichten basiert eine `CDaoRecordView` auf einer Dialogfeld Vorlage. DAO wird für Access-Datenbanken verwendet und wird von Office 2013 unterstützt. 3,6 ist die endgültige Version und wird als veraltet eingestuft.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Stellt eine direkt mit einem Open Database Connectivity (ODBC)-Recordset-Objekt verbundene Formularansicht bereit. Wie alle Formular Ansichten basiert eine `CRecordView` auf einer Dialogfeld Vorlage.

[CHtmlEditView](../mfc/reference/chtmleditview-class.md)<br/>
Eine Formularansicht, die die Funktionalität der Webbrowser-HTML-Bearbeitungs Plattform bereitstellt.

## <a name="control-views"></a>Steuerelement Ansichten

Steuerelement Ansichten zeigen ein Steuerelement als Ansicht an.

[Cctrlview](../mfc/reference/cctrlview-class.md)<br/>
Die Basisklasse für alle Sichten, die Windows-Steuerelementen zugeordnet sind. Die Sichten, die auf-Steuerelementen basieren, werden unten beschrieben.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Eine Ansicht, die ein Windows-Standard Bearbeitungs Steuerelement enthält (siehe [CEdit](../mfc/reference/cedit-class.md)). Bearbeitungs Steuerelemente unterstützen Textbearbeitungs-, Such-, Ersetzungs-und scrollfunktionen.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Eine Ansicht, die ein umfassendes Windows-Bearbeitungs Steuerelement enthält (siehe [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Zusätzlich zu den Funktionen eines Bearbeitungs Steuer Elements unterstützen Rich Edit-Steuerelemente Schriftarten, Farben, Absatz Formatierung und eingebettete OLE-Objekte.

[CListView](../mfc/reference/clistview-class.md)<br/>
Eine Ansicht, die ein Windows-Listen Steuerelement enthält (siehe [CListCtrl](../mfc/reference/clistctrl-class.md)). Ein Listen Steuerelement zeigt eine Auflistung von Elementen an, die jeweils aus einem Symbol und einer Bezeichnung bestehen, ähnlich wie im rechten Bereich des Datei-Explorers.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Eine Ansicht, die ein Windows Tree-Steuerelement enthält (siehe [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). In einem Struktur Steuerelement wird eine hierarchische Liste von Symbolen und Bezeichnungen ähnlich wie im linken Bereich des Datei-Explorers angezeigt.

## <a name="related-classes"></a>Verwandte Klassen

`CSplitterWnd`ermöglicht es Ihnen, mehrere Ansichten innerhalb eines einzelnen Rahmen Fensters zu haben. `CPrintDialog`und `CPrintInfo` unterstützen die Druck-und Druckvorschau Fähigkeit von Sichten. `CRichEditDoc`und `CRichEditCntrItem` werden mit `CRichEditView` verwendet, um OLE-Container-Funktionen zu implementieren.

[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)<br/>
Ein Fenster, das der Benutzer in mehrere Bereiche aufteilen kann. Diese Bereiche können durch den Benutzer oder die Größe der Größe geändert werden.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Stellt ein Standard Dialogfeld zum Drucken einer Datei bereit.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
Eine-Struktur, die Informationen zu einem Druck-oder Druckvorschau Auftrag enthält. Wird von `CView`der Druck Architektur verwendet.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Verwaltet die Liste der OLE-Client Elemente, die in `CRichEditView`einem enthalten sind.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
Bietet Client seitigen Zugriff auf ein OLE-Element, das in `CRichEditView`einem gespeichert ist.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../mfc/class-library-overview.md)
