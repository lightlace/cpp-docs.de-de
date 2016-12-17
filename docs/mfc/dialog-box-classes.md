---
title: "Dialogfeldklassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.classes.dialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allgemeine Dialogfeldklassen"
  - "Dialogfeldklassen"
  - "OLE, allgemeine Dialogfeldklassen"
  - "Eigenschaftenblätter-Klassen"
  - "Registerkarten-Dialogfelder"
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Dialogfeldklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klasse `CDialog` und abgeleitete Klassen kapseln Dialogfeldfunktionalität.  Da ein Dialogfeld eine spezielle Fenster ist, wird `CDialog` von `CWnd` abgeleitet.  Leiten Sie die Dialogfeldklassen von `CDialog` oder eine der allgemeinen Dialogfeldklassen für Standarddialogfelder, wie Öffnen oder Speichern einer Datei ein, Drucken, einer Schriftart oder eine Farbe auswählen, einen Suche\-undREPLACE\-Vorgang starten, oder OLE\-verknüpfte verschiedene Vorgänge ausführen.  
  
 [CDialog\-Klasse](../mfc/reference/cdialog-class.md)  
 Die Basisklasse für alle Dialogfelder, modal und nicht modale.  
  
 [CDataExchange](../mfc/reference/cdataexchange-class.md)  
 Zubehördatenaustausch und Validierungsinformationen für Dialogfelder.  
  
## Allgemeine Dialogfelder  
 Diese Dialogfeldklassen kapseln die Windows\-häufig verwendetes Dialogfeld.  Sie stellen benutzerfreundliche Implementierungen von schwierigen Dialogfeldern.  
  
 [CCommonDialog](../mfc/reference/ccommondialog-class.md)  
 Basisklasse für alle Standarddialogfelder.  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 Stellt ein Standarddialogfeld zum Öffnen oder Speichern einer Datei.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Stellt ein Standarddialogfeld zum Auswählen einer Farbe zur Verfügung.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Stellt ein Standarddialogfeld für das Auswählen einer Schriftart zur Verfügung.  
  
 [CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)  
 Stellt ein Standarddialogfeld für einen Suche\-undREPLACE\-Vorgang bereit.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Stellt ein Standarddialogfeld zum Drucken einer Datei.  
  
 [CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)  
 Stellt ein Windows 2000\-Druckeigenschaftenblatt bereit.  
  
 [CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)  
 Kapselt die Dienste, die allgemeine Seiteneinrichtungsdialogfeld Windows mit zusätzlicher Unterstützung für das Festlegen und Ändern von Druckrändern bereitgestellt werden.  
  
## OLE\-Common\-Dialogfelder  
 OLE werden mehrere Standarddialogfelder Windows hinzu.  Diese Klassen kapseln die OLE\-häufig verwendetes Dialogfeld.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Wird vom Framework, um allgemeine Implementierungen für alle OLE\-Dialogfelder zu enthalten.  Alle Dialogfeldklassen in der Benutzeroberflächekategorie werden von dieser Basisklasse abgeleitet.  `COleDialog` kann nicht direkt verwendet werden.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Zeigt das EINFG\-Objektdialogfeld, die Standardbenutzeroberfläche für Einfügen von neuen eingebetteten oder verknüpften Elemente OLE an.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Zeigt das Inhalte einfügen\-Dialogfeld, die Standardbenutzeroberfläche für das Implementieren des Bearbeitungs\-Inhalte einfügen\-Befehls an.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Zeigt das Bearbeitungs\-Linkdialogfeld, die Standardbenutzeroberfläche für das Ändern von Informationen über verknüpfte Elemente.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Zeigt das Änderungs\-Symboldialogfeld, die Standardbenutzeroberfläche für das Ändern des Symbols an, das mit einem eingebetteten oder verknüpften OLE Element zugeordnet ist.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Zeigt das Bekehrtdialogfeld, die Standardbenutzeroberfläche für das Konvertieren von OLE\-Elementen von einem Typ zu anderen an.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Kapselt das häufig verwendete OLE Eigenschaftendialogfeld Windows.  Allgemeine OLE\-Eigenschaftendialogfelder bieten eine einfache Möglichkeit, Eigenschaften eines OLE\-Dokumentelements anzuzeigen und zu ändern, das mit Windows\-Standards in ähnlicher Weise konsistent ist.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Zeigt das Updatedialogfeld, die Standardbenutzeroberfläche für das Aktualisieren aller Links in einem Dokument an.  Das Dialogfeld enthält eine Statusanzeige, um anzugeben, wie nahe die Updateprozedur abgeschlossen ist.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Zeigt das Änderungs\-Quelldialogfeld, die Standardbenutzeroberfläche für das Ändern des Ziels oder der Quelle eines Links an.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Zeigt den Server ausgelastete und des Servers nicht Reaktionsdialogfelder, die Standardbenutzeroberfläche für die Behandlung der Aufrufe von ausgelasteten Anwendungen an.  Normalerweise automatisch angezeigt von der Implementierung. [COleMessageFilter](../mfc/reference/colemessagefilter-class.md)  
  
## Eigenschaftenblatt\-Klassen  
 Die Eigenschaftenblattklassen ermöglichen der Anwendungen, Eigenschaftenblätter, auch als Dialogfelder verwenden im Registerkartenformat.  Eigenschaftenblätter sind eine effiziente Möglichkeit, viele Steuerelemente in einem einzigen Dialogfeld zu organisieren.  
  
 [CPropertyPage](../mfc/reference/cpropertypage-class.md)  
 Stellt die einzelnen Seiten innerhalb eines Eigenschaftenblatts bereit.  Leiten Sie eine Klasse von `CPropertyPage`, dass jede Seite dem Eigenschaftenblatt hinzugefügt werden kann.  
  
 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)  
 Stellt die Frames für mehrere Eigenschaftenseiten bereit.  Leiten Sie die Eigenschaftenblattklasse von `CPropertySheet`, um die Eigenschaftenblätter schnell zu implementieren.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Zeigt die Eigenschaften eines OLE\-Steuerelements in einer grafischen Oberfläche an, ähnlich einem Dialogfeld.  
  
## Dialogfeldklassen HTML\-basierte  
 [CDHtmlDialog](../mfc/reference/cdhtmldialog-class.md)  
 Wird verwendet, um Dialogfelder zu erstellen, die die Benutzeroberfläche mit HTML anstatt Dialogfeldressourcen implementieren.  
  
 [CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)  
 Zeigt mehrere HTML\-Seiten sequenziell an und behandelt die Ereignisse von jeder Seite.  
  
## Verwandte Klassen  
 Diese Klassen sind nicht Dialogfelder an, nutzen jedoch Dialogfeldvorlagen und haben viele des Verhaltens der Dialogfelder.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Eine Steuerleiste, die auf einer Dialogvorlage ist.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Eine Bildlaufansicht, deren Layout in einer Dialogfeldvorlage definiert wird.  Leiten Sie eine Klasse von `CFormView`, um eine Benutzeroberfläche auf einer Dialogfeldvorlage zu implementieren.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Stellt eine Formularansicht bereit, die direkt an ein Datenzugriffsobjekt \(dao\)\- Recordset\-Objekt verbunden ist.  Wie alle Formularansichten ist `CDaoRecordView` auf einer Dialogfeldvorlage.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Stellt eine Formularansicht bereit, die direkt mit einem Recordset\-Objekt verbunden wird der Open Database Connectivity \(ODBC\).  Wie alle Formularansichten ist `CRecordView` auf einer Dialogfeldvorlage.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 Eine Struktur, die Informationen über einen Drucks\- oder Seitenansichtsauftrag enthält.  Wird von der Druckarchitektur von [CView](../mfc/reference/cview-class.md).  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)