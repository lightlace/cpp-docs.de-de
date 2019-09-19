---
title: Ansichtsklassen (Architektur)
ms.date: 09/17/2019
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
ms.openlocfilehash: c6c1272d41eb7a01ec5a7ee10fadb4ab21547ce7
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096054"
---
# <a name="view-classes-architecture"></a>Ansichtsklassen (Architektur)

`CView`und die abgeleiteten Klassen sind untergeordnete Fenster, die den Client Bereich eines Rahmen Fensters darstellen. Sichten zeigen Daten an und akzeptieren Eingaben für ein Dokument.

Eine Ansichts Klasse wird mithilfe eines Document-Template-Objekts einer Dokument Klasse und einer Rahmen Fenster Klasse zugeordnet.

[CView](../mfc/reference/cview-class.md)<br/>
Die Basisklasse für anwendungsspezifische Ansichten der Daten eines Dokuments. Sichten zeigen Daten an und akzeptieren Benutzereingaben, um die Daten zu bearbeiten oder auszuwählen. Leiten Sie Ihre Ansichts Klassen von ab `CView`.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Die Basisklasse für Ansichten mit scrollfunktionen. Leiten Sie Ihre Ansichts `CScrollView` Klasse von für den automatischen Bildlauf ab.

## <a name="form-and-record-views"></a>Formular-und Daten Satz Sichten

Formular Ansichten sind auch scrollansichten. Sie basieren auf einer Dialogfeld Vorlage.

Daten Satz Sichten werden von Formular Ansichten abgeleitet. Zusätzlich zu der Dialogfeld Vorlage haben Sie auch eine Verbindung mit einer-Datenbank.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Eine scrollansicht, deren Layout in einer Dialogfeld Vorlage definiert ist. Leiten Sie eine Klasse `CFormView` von ab, um eine Benutzeroberfläche zu implementieren, die auf einer Dialogfeld Vorlage basiert.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Stellt eine Formularansicht bereit, die direkt mit einem DAO-Recordset-Objekt (Data Access Object) verbunden ist. Wie alle Formular Ansichten basiert eine `CDaoRecordView` auf einer Dialogfeld Vorlage. DAO wird für Access-Datenbanken verwendet und wird von Office 2013 unterstützt. 3,6 ist die endgültige Version und wird als veraltet eingestuft.

[CHtmlView](../mfc/reference/chtmlview-class.md)<br/>
Unterstützt ein Steuerelement für das Webbrowsen innerhalb einer Anwendung. Das-Steuerelement unterstützt Dynamic HTML in MFC.

[COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)<br/>
Stellt MFC-OLE DB Unterstützung für Formular Ansichten bereit.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Stellt eine direkt mit einem Open Database Connectivity (ODBC)-Recordset-Objekt verbundene Formularansicht bereit. Wie alle Formular Ansichten basiert eine `CRecordView` auf einer Dialogfeld Vorlage.

## <a name="control-views"></a>Steuerelement Ansichten

Steuerelement Ansichten zeigen ein Steuerelement als Ansicht an.

[Cctrlview](../mfc/reference/cctrlview-class.md)<br/>
Die Basisklasse für alle Sichten, die Windows-Steuerelementen zugeordnet sind. Die Sichten, die auf-Steuerelementen basieren, werden unten beschrieben.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Eine Ansicht, die ein Windows-Standard Bearbeitungs Steuerelement enthält (siehe [CEdit](../mfc/reference/cedit-class.md)). Bearbeitungs Steuerelemente unterstützen Textbearbeitungs-, Such-, Ersetzungs-und scrollfunktionen.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Eine Ansicht, die ein umfassendes Windows-Bearbeitungs Steuerelement enthält (siehe [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Zusätzlich zu den Funktionen eines Bearbeitungs Steuer Elements unterstützen Rich Edit-Steuerelemente Schriftarten, Farben, Absatz Formatierung und eingebettete OLE-Objekte.

[CListView](../mfc/reference/clistview-class.md)<br/>
Eine Ansicht, die ein Windows-Listen Steuerelement enthält (siehe [CListCtrl](../mfc/reference/clistctrl-class.md)). Ein Listen Steuerelement zeigt Symbole und Zeichen folgen auf ähnliche Weise wie im rechten Bereich des Datei-Explorers an.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Eine Ansicht, die ein Windows Tree-Steuerelement enthält (siehe [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). In einem Struktur Steuerelement werden Symbole und Zeichen folgen, die in einer Hierarchie angeordnet sind, ähnlich wie im linken Bereich des Datei-Explorers angezeigt.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../mfc/class-library-overview.md)
