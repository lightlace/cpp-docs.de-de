---
title: Dialogfeldklassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.dialog
dev_langs:
- C++
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60d33289d8025d7cdcaf4f6f69062230730b958c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dialog-box-classes"></a>Dialogfeldklassen
Klasse `CDialog` und die abgeleiteten Klassen kapseln Dialogfeld-Funktionalität. Da ein Dialogfeld eine besondere Art von Fenster ist `CDialog` stammt aus `CWnd`. Leiten Sie Ihre Dialogfeldklassen aus `CDialog` oder verwenden Sie eines der allgemeine Dialogfeldklassen für Dialogfelder "standard", z. B. Öffnen oder Speichern einer Datei, drucken, Auswählen einer Schriftart oder die Farbe, initiiert einen Vorgang suchen und ersetzen oder Durchführen von verschiedenen OLE-bezogene DDL-Vorgänge.  
  
 [CDialog](../mfc/reference/cdialog-class.md)  
 Die Basisklasse für alle Dialogfelder, modale und nicht modale.  
  
 [CDataExchange](../mfc/reference/cdataexchange-class.md)  
 Stellt Informationen zu Dialogdatenaustausch und-Validierung für Dialogfelder bereit.  
  
## <a name="common-dialogs"></a>(Allgemeine Dialoge)  
 Diese Dialogfeldklassen kapseln die allgemeine Windows-Dialogfelder. Sie bieten einfach zu bedienenden Implementierungen von komplizierte Dialogfelder.  
  
 [CCommonDialog](../mfc/reference/ccommondialog-class.md)  
 Die Basisklasse für alle Dialogfelder "common".  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 Stellt ein Standarddialogfeld zum Öffnen oder Speichern einer Datei an.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Stellt ein Standarddialogfeld für eine Farbe auswählen.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Stellt ein Standarddialogfeld zum Auswählen einer Schriftart an.  
  
 [CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)  
 Stellt ein Standarddialogfeld für einen Vorgang suchen und ersetzen.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Stellt ein Standarddialogfeld zum Drucken einer Datei an.  
  
 [CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)  
 Stellt ein Windows-druckeigenschaftenblatt bereit.  
  
 [CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)  
 Kapselt die Dienste von Seiteneinrichtung-Standarddialogfeld Windows mit zusätzlicher Unterstützung für das Festlegen und Ändern von druckrändern.  
  
## <a name="ole-common-dialogs"></a>OLE-Standarddialogfelder  
 OLE hinzugefügt Windows einige häufig verwendete Dialogfelder. Diese Klassen kapseln, die häufig verwendete OLE-Dialogfelder.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Vom Framework verwendet, um häufige Anwendungsbereiche für alle OLE-Dialogfelder enthalten. Alle in der Benutzeroberfläche Kategorie Dialogfeldklassen werden von dieser Basisklasse abgeleitet. `COleDialog` kann nicht direkt verwendet werden.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Objekt einfügen zeigt das Dialogfeld an, die Standardbenutzeroberfläche für das Einfügen von neuen OLE Verknüpfte oder eingebettete Elemente.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Fügen Sie spezielle zeigt das Dialogfeld an, die Standardbenutzeroberfläche zum Implementieren des Befehls Inhalte einfügen bearbeiten.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Zeigt das Dialogfeld Verknüpfungen bearbeiten, die Standardbenutzeroberfläche zum Ändern von Informationen zu verknüpften Elementen an.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Zeigt das Dialogfeld "Symbol ändern", die Standardbenutzeroberfläche ändern, die das OLE zugeordnete Symbol eingebettet oder verknüpften Elements an.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Zeigt das Dialogfeld konvertieren, die Standardbenutzeroberfläche für OLE-Elemente von einem Typ in einen anderen konvertieren.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Kapselt das Windows allgemeine OLE-Eigenschaften-Dialogfeld an. Häufig verwendete Dialogfelder für OLE-Eigenschaften bieten eine einfache Möglichkeit zum Anzeigen und ändern die Eigenschaften eines Elements ein OLE-Dokument in Übereinstimmung mit den Windows-Standards.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Zeigt das Update (Dialogfeld), die Standardbenutzeroberfläche für alle Links in einem Dokument aktualisieren. Das Dialogfeld enthält eine Statusanzeige eingeblendet, um festzulegen, wie nahe die Updateprozedur bis zum Abschluss.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Ändern der Quelle zeigt das Dialogfeld an, die standard-Benutzeroberfläche für die Quell- oder einer Verknüpfung ändern.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Zeigt die Server ausgelastet "und" Server antwortet nicht-Dialogfelder, die Standardbenutzeroberfläche Aufrufe für ausgelastete Anwendungen zu behandeln. Angezeigt in der Regel automatisch von der [COleMessageFilter](../mfc/reference/colemessagefilter-class.md) Implementierung.  
  
## <a name="property-sheet-classes"></a>Eigenschaftenblätter-Klassen  
 Die Eigenschaftenblätter-Klassen ermöglichen Anwendungen Eigenschaftenblättern, auch bekannt als Registerkarten-Dialogfeldern zu verwenden. Eigenschaftenblätter sind eine effiziente Möglichkeit, eine große Anzahl von Steuerelementen in einem einzelnen Dialogfeld Organisieren.  
  
 [CPropertyPage](../mfc/reference/cpropertypage-class.md)  
 Stellt die einzelnen Seiten in einem Eigenschaftenblatt. Leiten Sie eine Klasse von `CPropertyPage` für jede Seite der Eigenschaftenseite hinzugefügt werden.  
  
 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)  
 Mehrere Eigenschaftenseiten bereit den Frame. Leiten Sie eine Eigenschaft Sheet-Klasse aus `CPropertySheet` Ihre Eigenschaftenblätter schnell und einfach implementieren.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Zeigt die Eigenschaften des OLE in einer grafischen Oberfläche, ähnlich wie in einem Dialogfeld zu steuern.  
  
## <a name="html-based-dialog-classes"></a>HTML-basierten Dialogfeldklassen  
 [CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)  
 Verwendet, um Dialogfelder zu erstellen, die ihre Benutzeroberfläche HTML statt Dialogfeld Ressourcen zu implementieren.  
  
 [CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)  
 Zeigt mehrere HTML-Seiten sequenziell und behandelt die Ereignisse jeder Seite.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 Diese Klassen sind pro se nicht Dialogfelder, aber sie Dialogfeldvorlagen verwenden und haben ein Großteil des Verhaltens von Dialogfeldern.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Eine Steuerleiste, die auf einer Dialogfeldvorlage basiert.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Eine Scroll-Sicht, deren Layout in einer Dialogfeldvorlage definiert ist. Leiten Sie eine Klasse von `CFormView` eine Benutzeroberfläche, die basierend auf einer Dialogfeldvorlage implementieren.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Stellt eine Form anzeigen, die direkt mit einem Recordset-Objekt (Datenzugriffsobjekt) verbunden. Alle Formularansichten, wie eine `CDaoRecordView` basiert auf einer Dialogfeldvorlage.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Stellt eine Form anzeigen, die direkt mit einer Open Database Connectivity (ODBC)-Recordset-Objekt verbunden. Alle Formularansichten, wie eine `CRecordView` basiert auf einer Dialogfeldvorlage.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 Eine Struktur, die Informationen zu einem Auftrag Druckauftrags oder seitenansichtauftrags enthält. Verwendet die Drucken Architektur der [CView](../mfc/reference/cview-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

