---
title: Ansichtsklassen (Architektur)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
ms.openlocfilehash: 7855f152e340b488d64f01dbf290034e1bdbc9b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647296"
---
# <a name="view-classes-architecture"></a>Ansichtsklassen (Architektur)

`CView` und die abgeleiteten Klassen sind untergeordnete Fenster, die darstellen, das den Clientbereich eines Rahmenfensters. Ansichten Daten anzeigen und akzeptieren eine Eingabe für ein Dokument.

Eine Ansichtsklasse ist mit einer Dokumentklasse und einem Rahmenfenster (Klasse) mit einem Dokumentvorlagen-Objekt zugeordnet.

[CView](../mfc/reference/cview-class.md)<br/>
Die Basisklasse für anwendungsspezifische Sichten der Daten eines Dokuments. Ansichten anzeigen von Daten und Benutzereingaben, um zu bearbeiten, oder wählen Sie die Daten akzeptieren. Leiten Sie Ihre Ansicht Klassen verfügen über `CView`.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Die Basisklasse für Ansichten mit Bildlauffunktionen. Ableiten der Klasse "View" aus `CScrollView` für den automatischen Bildlauf.

## <a name="form-and-record-views"></a>Formular und Datensatzansichten

Formularansichten sind auch Ansichten Bildlauf. Sie basiert auf einer Dialogfeldvorlage.

Datensatzansichten werden von Formularansichten abgeleitet. Zusätzlich zu der Dialogfeldvorlage haben sie auch eine Verbindung mit einer Datenbank.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Eine Bildlaufansicht, deren Layout in eine Dialogfeldvorlage definiert ist. Leiten Sie eine Klasse von `CFormView` zur Implementierung einer Benutzeroberfläche, die basierend auf einer Dialogfeldvorlage.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Stellt eine Form anzeigen, die direkt mit einem Recordset-Objekt (Data Access Object, DAO) verbunden. Alle Formularansichten, wie eine `CDaoRecordView` basiert auf einer Dialogfeldvorlage.

[CHtmlView](../mfc/reference/chtmlview-class.md)<br/>
Unterstützt ein Steuerelement für das Browsen im Web in einer Anwendung. Unterstützung für dynamic HTML des Steuerelements in MFC.

[COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)<br/>
Stellt MFC-OLE DB-Unterstützung, die für Formularansichten.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Stellt eine Form anzeigen, die direkt mit einer Open Database Connectivity (ODBC)-Recordset-Objekt verbunden. Alle Formularansichten, wie eine `CRecordView` basiert auf einer Dialogfeldvorlage.

## <a name="control-views"></a>Steuerelementansicht

Steuerelementansicht Steuerelement, die als ihre Ansicht angezeigt wird.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Die Basisklasse für alle Ansichten, die Windows-Steuerelementen zugeordnet. Die Ansichten, die basierend auf werden nachfolgend beschrieben.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Bearbeitungssteuerelement für eine Sicht, einen Windows-Standard enthält (siehe [CEdit](../mfc/reference/cedit-class.md)). Bearbeiten Sie die Steuerelemente unterstützen Text-Bearbeitung, suchen, ersetzen und Bildlauffunktionen.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Eine Ansicht, enthält eine umfassende Windows-Bearbeitungssteuerelement (finden Sie unter [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Zusätzlich zu den Funktionen eines Steuerelements bearbeiten Bearbeiten umfangreiche Steuerelemente unterstützen Schriftarten, Farben, absatzformatierung und eingebettete OLE-Objekte.

[CListView](../mfc/reference/clistview-class.md)<br/>
Eine Sicht, ein Windows-Steuerelement enthält (siehe [CListCtrl](../mfc/reference/clistctrl-class.md)). Ein Listensteuerelement zeigt Symbole und Zeichenfolgen ähnlich wie in den rechten Bereich des Datei-Explorers.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Eine Sicht, ein Windows-Strukturansicht-Steuerelement enthält (siehe [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Ein Strukturansicht-Steuerelement zeigt Symbole und Zeichenfolgen, die in einer Hierarchie auf ähnliche Weise auf den linken Bereich des Datei-Explorers angeordnet.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

