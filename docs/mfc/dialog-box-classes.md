---
title: Dialogfeldklassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.dialog
helpviewer_keywords:
- property sheet classes
- dialog box classes
- OLE common dialog classes
- common dialog classes [MFC]
- tab dialog boxes
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
ms.openlocfilehash: 3533a548f009a65462ce0d821d782db0ada9aa4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490004"
---
# <a name="dialog-box-classes"></a>Dialogfeldklassen

Klasse `CDialog` und ihrer abgeleiteten Klassen kapseln die Dialogfeld-Funktionalität. Da ein Dialogfeld, das eine spezielle Art von Fenster wird `CDialog` ergibt sich aus `CWnd`. Leiten Sie Ihre Klassen von `CDialog` oder verwenden Sie eine von der Standarddialogfeld-Klassen für Standarddialogfelder, z. B. Öffnen oder Speichern einer Datei, drucken, Auswählen einer Schriftart oder Farbe, initiieren Sie einen Suchen / Ersetzen-Vorgang oder Ausführen von verschiedenen OLE-bezogene Vorgänge.

[CDialog](../mfc/reference/cdialog-class.md)<br/>
Die Basisklasse für alle Dialogfelder, modale und nicht modale.

[CDataExchange](../mfc/reference/cdataexchange-class.md)<br/>
Stellt Daten Dialogdatenaustausch und-Validierung Informationen für Dialogfelder bereit.

## <a name="common-dialogs"></a>(Allgemeine Dialoge)

Diese Dialogfeldklassen kapseln, die Windows-Standarddialogfelder. Sie bieten eine einfach zu bedienende Implementierungen von Dialogfeldern für kompliziert.

[CCommonDialog](../mfc/reference/ccommondialog-class.md)<br/>
Basisklasse für alle Standarddialogfelder.

[CFileDialog](../mfc/reference/cfiledialog-class.md)<br/>
Stellt ein Standarddialogfeld für öffnen oder Speichern einer Datei bereit.

[CColorDialog](../mfc/reference/ccolordialog-class.md)<br/>
Stellt ein Standarddialogfeld für die Auswahl einer Farbe bereit.

[CFontDialog](../mfc/reference/cfontdialog-class.md)<br/>
Stellt ein Standarddialogfeld für das Auswählen einer Schriftart an.

[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)<br/>
Stellt ein Standarddialogfeld für ein Suchen / Ersetzen-Vorgang bereit.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Stellt ein Standarddialogfeld zum Drucken einer Datei bereit.

[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)<br/>
Stellt ein Windows-druckeigenschaftenblatt bereit.

[CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)<br/>
Kapselt die Dienste, die im Dialogfeld allgemeine Seiteneinrichtung Windows und stellt zusätzliche Unterstützung für das Festlegen und Ändern von druckrändern bereitgestellt.

## <a name="ole-common-dialogs"></a>OLE-Standarddialogfelder

OLE hinzugefügt Windows mehrere Standarddialogfelder. Diese Klassen kapseln die OLE-Standarddialogfelder.

[COleDialog](../mfc/reference/coledialog-class.md)<br/>
Häufige Anwendungsbereiche für alle OLE-Dialogfelder enthalten verwendet vom Framework. Alle Dialogfeldklassen in der Kategorie der Benutzeroberfläche werden von dieser Basisklasse abgeleitet. `COleDialog` kann nicht direkt verwendet werden.

[COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)<br/>
Objekt einfügen zeigt das Dialogfeld an, die Standardbenutzeroberfläche für das Einfügen von neuen OLE Verknüpfte oder eingebettete Elemente.

[COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)<br/>
Fügen Sie spezielle zeigt das Dialogfeld an, die Standardbenutzeroberfläche zum Implementieren des Befehls Inhalte einfügen bearbeiten.

[COleLinksDialog](../mfc/reference/colelinksdialog-class.md)<br/>
Verknüpfungen bearbeiten zeigt das Dialogfeld an, die Standardbenutzeroberfläche zum Ändern von Informationen zu verknüpften Elementen.

[COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)<br/>
Zeigt das Dialogfeld "Symbol ändern", die Standardbenutzeroberfläche für ändern, das ein OLE zugeordnete Symbol eingebettet, oder verknüpftes Element an.

[COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)<br/>
Zeigt das Dialogfeld konvertieren, die Standardbenutzeroberfläche für die Konvertierung von OLE-Elementen von einem Typ in einen anderen.

[COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)<br/>
Kapselt das Windows allgemeine OLE-Eigenschaften-Dialogfeld. OLE-Eigenschaften-Standarddialogfelder bieten eine einfache Möglichkeit zum Anzeigen und ändern die Eigenschaften eines Elements des OLE-Dokument in Übereinstimmung mit den Windows-Standards.

[COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)<br/>
Update zeigt das Dialogfeld an, die Standardbenutzeroberfläche für alle Links in einem Dokument zu aktualisieren. Das Dialogfeld enthält eine Statusanzeige, um anzugeben, wie nahe die Updateprozedur abgeschlossen ist.

[COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)<br/>
Quelle ändern zeigt das Dialogfeld an, die Standardbenutzeroberfläche für das Ändern der Ziel- oder eines Links.

[COleBusyDialog](../mfc/reference/colebusydialog-class.md)<br/>
Zeigt die Server ausgelastet "und" Server nicht geantwortet-Dialogfelder, die Standardbenutzeroberfläche Aufrufe für ausgelastete Anwendungen zu behandeln. Normalerweise automatisch vom angezeigt, die [COleMessageFilter](../mfc/reference/colemessagefilter-class.md) Implementierung.

## <a name="property-sheet-classes"></a>Eigenschaftenblätter-Klassen

Der Eigenschaftenblätter-Klassen ermöglichen den Anwendungen Eigenschaftenblätter, auch bekannt als Registerkarten-Dialogfelder zu verwenden. Eigenschaftenblätter sind eine effiziente Möglichkeit, eine große Anzahl von Steuerelementen in einem einzelnen Dialogfeld zu organisieren.

[CPropertyPage](../mfc/reference/cpropertypage-class.md)<br/>
Enthält die einzelnen Seiten innerhalb eines Eigenschaftenblatts an. Leiten Sie eine Klasse von `CPropertyPage` für jede Seite Ihre Eigenschaftenblatt hinzugefügt werden.

[CPropertySheet](../mfc/reference/cpropertysheet-class.md)<br/>
Stellt den Frame für mehrere Eigenschaftenseiten bereit. Leiten Sie die Eigenschaft Sheet-Klasse aus `CPropertySheet` Ihre Eigenschaftenblätter schnell zu implementieren.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
Zeigt steuern Sie die Eigenschaften von einer OLE in eine grafische Oberfläche, ähnlich wie ein Dialogfeld.

## <a name="html-based-dialog-classes"></a>HTML-basierte Dialogfeldklassen

[CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)<br/>
Verwendet, um Dialogfelder zu erstellen, die ihre Benutzeroberfläche HTML statt der Dialogfeld-Ressourcen zu implementieren.

[CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)<br/>
Mehrere HTML-Seiten sequenziell zeigt an, und behandelt die Ereignisse jeder Seite.

## <a name="related-classes"></a>Verwandte Klassen

Diese Klassen sind sich nicht Dialogfelder, aber sie haben das Verhalten von Dialogfeldern und Verwenden von Dialogfeldvorlagen.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
Eine Steuerleiste, die auf eine Dialogfeldvorlage basieren.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Eine Bildlaufansicht, deren Layout in eine Dialogfeldvorlage definiert ist. Leiten Sie eine Klasse von `CFormView` zur Implementierung einer Benutzeroberfläche, die basierend auf einer Dialogfeldvorlage.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Stellt eine Form anzeigen, die direkt mit einem Recordset-Objekt (Data Access Object, DAO) verbunden. Alle Formularansichten, wie eine `CDaoRecordView` basiert auf einer Dialogfeldvorlage.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Stellt eine Form anzeigen, die direkt mit einer Open Database Connectivity (ODBC)-Recordset-Objekt verbunden. Alle Formularansichten, wie eine `CRecordView` basiert auf einer Dialogfeldvorlage.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
Eine Struktur, die Informationen zu einem Auftrag des Druckauftrags oder seitenansichtauftrags enthält. Verwendet die Drucken Architektur der [CView](../mfc/reference/cview-class.md).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

