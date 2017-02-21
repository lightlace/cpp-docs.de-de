---
title: "CFileDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileDialog class"
  - "common file dialog boxes"
  - "Dialogfelder, common"
ms.assetid: fda4fd3c-08b8-4ce0-8e9d-7bab23f8c6c0
caps.latest.revision: 47
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 49
---
# CFileDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt das Standarddialogfelder, das für die geöffnete Datei oder die Dateispeichervorgänge verwendet wird.  
  
## Syntax  
  
```  
class CFileDialog : public CCommonDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md)|Erstellt ein `CFileDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFileDialog::AddCheckButton](../Topic/CFileDialog::AddCheckButton.md)|Fügt eine Überprüfungsschaltfläche im Dialogfeld hinzugefügt.|  
|[CFileDialog::AddComboBox](../Topic/CFileDialog::AddComboBox.md)|Fügt ein Kombinationsfeld im Dialogfeld hinzugefügt.|  
|[CFileDialog::AddControlItem](../Topic/CFileDialog::AddControlItem.md)|Fügt ein Element einem Containersteuerelement im Dialogfeld hinzu.|  
|[CFileDialog::AddEditBox](../Topic/CFileDialog::AddEditBox.md)|Fügt ein Eingabefeld im Dialogfeld hinzugefügt.|  
|[CFileDialog::AddMenu](../Topic/CFileDialog::AddMenu.md)|Fügt ein Menü im Dialogfeld hinzugefügt.|  
|[CFileDialog::AddPlace](../Topic/CFileDialog::AddPlace.md)|Überladen.  Fügt einen Ordner der Liste der Stellen hinzu, damit der Benutzer die Elemente verfügbar sind, öffnet oder gespeichert wird.|  
|[CFileDialog::AddPushButton](../Topic/CFileDialog::AddPushButton.md)|Fügt eine Schaltfläche im Dialogfeld hinzugefügt.|  
|[CFileDialog::AddRadioButtonList](../Topic/CFileDialog::AddRadioButtonList.md)|Fügt eine Gruppe des Optionsfelds \(auch als Optionsfeld\) im Dialogfeld hinzugefügt.|  
|[CFileDialog::AddSeparator](../Topic/CFileDialog::AddSeparator.md)|Fügt ein Trennzeichen im Dialogfeld hinzugefügt.|  
|[CFileDialog::AddText](../Topic/CFileDialog::AddText.md)|Fügt Textinhalt im Dialogfeld hinzugefügt.|  
|[CFileDialog::ApplyOFNToShellDialog](../Topic/CFileDialog::ApplyOFNToShellDialog.md)|Aktualisiert den Zustand `CFileDialog`, um die Parameter und die Flags entsprechen, die in der `m_ofn`\-Membervariable gespeichert werden.|  
|[CFileDialog::DoModal](../Topic/CFileDialog::DoModal.md)|Zeigt das Dialogfeld an und ermöglicht es dem Benutzer, um die Auswahl zu machen.|  
|[CFileDialog::EnableOpenDropDown](../Topic/CFileDialog::EnableOpenDropDown.md)|Aktiviert eine Dropdownliste der **Öffnen** oder Schaltfläche **Speichern** im Dialogfeld.|  
|[CFileDialog::EndVisualGroup](../Topic/CFileDialog::EndVisualGroup.md)|Beendet die Einführung von Elementen zu einer visuellen Gruppe im Dialogfeld.|  
|[CFileDialog::GetCheckButtonState](../Topic/CFileDialog::GetCheckButtonState.md)|Ruft den aktuellen Zustand einer Überprüfungsschaltfläche \(Kontrollkästchen\) im Dialogfeld.|  
|[CFileDialog::GetControlItemState](../Topic/CFileDialog::GetControlItemState.md)|Ruft den aktuellen Zustand eines Elements in einem Containersteuerelement ab, das im Dialogfeld gefunden wird.|  
|[CFileDialog::GetControlState](../Topic/CFileDialog::GetControlState.md)|Ruft die aktuelle Sichtbarkeit und die aktivierten Zustände eines angegebenen Steuerelements ab.|  
|[CFileDialog::GetEditBoxText](../Topic/CFileDialog::GetEditBoxText.md)|Ruft den aktuellen Text in einem Eingabefeldsteuerelement ab.|  
|[CFileDialog::GetFileExt](../Topic/CFileDialog::GetFileExt.md)|Gibt die Erweiterung der ausgewählten Datei zurück.|  
|[CFileDialog::GetFileName](../Topic/CFileDialog::GetFileName.md)|Gibt den Dateinamen der ausgewählten Datei zurück.|  
|[CFileDialog::GetFileTitle](../Topic/CFileDialog::GetFileTitle.md)|Gibt den Titel der ausgewählten Datei zurück.|  
|[CFileDialog::GetFolderPath](../Topic/CFileDialog::GetFolderPath.md)|Ruft den Pfad des aktuell geöffneten Ordners oder des Verzeichnisses für ein sowie **Öffnen** oder **Speichern unter** Standarddialogfelder ab.|  
|[CFileDialog::GetIFileDialogCustomize](../Topic/CFileDialog::GetIFileDialogCustomize.md)|Ruft das interne COM\-Objekt für ein benutzerdefiniertes `CFileDialog`\-Objekt ab.|  
|[CFileDialog::GetIFileOpenDialog](../Topic/CFileDialog::GetIFileOpenDialog.md)|Ruft das interne COM\-Objekt für `CFileDialog` ab, das als **Öffnen** Dateidialogfeld verwendet wird.|  
|[CFileDialog::GetIFileSaveDialog](../Topic/CFileDialog::GetIFileSaveDialog.md)|Ruft das interne COM\-Objekt für `CFileDialog` ab, das als **Speichern** Dateidialogfeld verwendet wird.|  
|[CFileDialog::GetNextPathName](../Topic/CFileDialog::GetNextPathName.md)|Gibt den vollständigen Pfad der nächste ausgewählten Datei zurück.|  
|[CFileDialog::GetOFN](../Topic/CFileDialog::GetOFN.md)|Ruft die `OPENFILENAME`\-Struktur des `CFileDialog`\-Objekts ab.|  
|[CFileDialog::GetPathName](../Topic/CFileDialog::GetPathName.md)|Gibt den vollständigen Pfad der ausgewählten Datei zurück.|  
|[CFileDialog::GetReadOnlyPref](../Topic/CFileDialog::GetReadOnlyPref.md)|Gibt den schreibgeschützten Status der ausgewählten Datei zurück.|  
|[CFileDialog::GetResult](../Topic/CFileDialog::GetResult.md)|Ruft die von ab, die der Benutzer im Dialogfeld hat.|  
|[CFileDialog::GetResults](../Topic/CFileDialog::GetResults.md)|Ruft die Auswahl des Benutzers in einem Dialogfeld ab, das Mehrfachauswahl unterstützt.|  
|[CFileDialog::GetSelectedControlItem](../Topic/CFileDialog::GetSelectedControlItem.md)|Ruft ein bestimmtes Element von den angegebenen Containersteuerelementen im Dialogfeld.|  
|[CFileDialog::GetStartPosition](../Topic/CFileDialog::GetStartPosition.md)|Gibt die Position des ersten Elements der Namensliste zurück.|  
|[CFileDialog::HideControl](../Topic/CFileDialog::HideControl.md)|Blendet das angegebene Steuerelement in einem sowie **Öffnen** oder in **Speichern unter** Standarddialogfelder aus.|  
|[CFileDialog::IsPickFoldersMode](../Topic/CFileDialog::IsPickFoldersMode.md)|Bestimmt wenn das aktuelle im Dialogfeld Ordner\-Auswahlmodus.|  
|[CFileDialog::MakeProminent](../Topic/CFileDialog::MakeProminent.md)|Setzt ein Steuerelement im Dialogfeld, sodass es auf anderen hinzugefügten Steuerelemente verglichen wird.|  
|[CFileDialog::RemoveControlItem](../Topic/CFileDialog::RemoveControlItem.md)|Entfernt ein Element aus einem Containersteuerelement im Dialogfeld.|  
|[CFileDialog::SetCheckButtonState](../Topic/CFileDialog::SetCheckButtonState.md)|Legt den aktuellen Zustand einer Überprüfungsschaltfläche \(Kontrollkästchen\) im Dialogfeld fest.|  
|[CFileDialog::SetControlItemState](../Topic/CFileDialog::SetControlItemState.md)|Legt den aktuellen Zustand eines Elements in einem Containersteuerelement fest, das im Dialogfeld gefunden wird.|  
|[CFileDialog::SetControlItemText](../Topic/CFileDialog::SetControlItemText.md)|Legt den Text eines Steuerelements.  Zum Beispiel der Text, der ein Optionsfeld oder ein Element in einem Menü begleitet.|  
|[CFileDialog::SetControlLabel](../Topic/CFileDialog::SetControlLabel.md)|Legt den Text fest, der mit einem \- Steuerelement, wie Schaltflächentext oder einer Eingabefeldbezeichnung zugeordnet ist.|  
|[CFileDialog::SetControlState](../Topic/CFileDialog::SetControlState.md)|Legt die aktuelle Sichtbarkeit und die aktivierten Zustände eines angegebenen Steuerelements fest.|  
|[CFileDialog::SetControlText](../Topic/CFileDialog::SetControlText.md)|Legt den Text für das angegebene Steuerelement in einem sowie **Öffnen**  oder in **Speichern unter** Standarddialogfelder fest.|  
|[CFileDialog::SetDefExt](../Topic/CFileDialog::SetDefExt.md)|Legt die Standard\-Dateinamenerweiterung für ein sowie **Öffnen** oder **Speichern unter** Standarddialogfelder fest.|  
|[CFileDialog::SetEditBoxText](../Topic/CFileDialog::SetEditBoxText.md)|Legt den aktuellen Text in einem Eingabefeldsteuerelement fest.|  
|[CFileDialog::SetProperties](../Topic/CFileDialog::SetProperties.md)|Stellt einen Eigenschaftspeicher bereit, der die für definiert das Element verwendet werden, Standardwerte, die gespeichert wird.|  
|[CFileDialog::SetSelectedControlItem](../Topic/CFileDialog::SetSelectedControlItem.md)|Legt den Auswahlzustand eines bestimmten Elements in einer Optionsfeldgruppe fest, oder Kombinationsfeld starten im Dialogfeld.|  
|[CFileDialog::SetTemplate](../Topic/CFileDialog::SetTemplate.md)|Legt die Dialogfeldvorlage für das `CFileDialog`\-Objekt fest.|  
|[CFileDialog::StartVisualGroup](../Topic/CFileDialog::StartVisualGroup.md)|Deklariert eine visuelle Gruppe im Dialogfeld.  Nachfolgende Aufrufe von allen "fügen" Methode hinzufügen diese Elemente dieser Gruppe hinzu.|  
|[CFileDialog::UpdateOFNFromShellDialog](../Topic/CFileDialog::UpdateOFNFromShellDialog.md)|Aktualisiert die Daten, die in der `m_ofn`\-Membervariable gespeichert werden, um den aktuellen Zustand des Dateidialogfelds übereinstimmt.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFileDialog::OnButtonClicked](../Topic/CFileDialog::OnButtonClicked.md)|Aufgerufen, wenn auf die Schaltfläche geklickt wird.|  
|[CFileDialog::OnCheckButtonToggled](../Topic/CFileDialog::OnCheckButtonToggled.md)|Aufgerufen, wenn das Kontrollkästchen deaktiviert\/überprüft wird.|  
|[CFileDialog::OnControlActivating](../Topic/CFileDialog::OnControlActivating.md)|Aufgerufen, wenn das Steuerelement aktiv ist.|  
|[CFileDialog::OnFileNameChange](../Topic/CFileDialog::OnFileNameChange.md)|Bearbeitet die `WM_NOTIFY CDN_SELCHANGE` Meldung.|  
|[CFileDialog::OnFileNameOK](../Topic/CFileDialog::OnFileNameOK.md)|Überprüft den Dateinamen, der im Dialogfeld eingegeben wird.|  
|[CFileDialog::OnFolderChange](../Topic/CFileDialog::OnFolderChange.md)|Bearbeitet die `WM_NOTIFY CDN_FOLDERCHANGE` Meldung.|  
|[CFileDialog::OnInitDone](../Topic/CFileDialog::OnInitDone.md)|Bearbeitet die `WM_NOTIFY CDN_INITDONE` Meldung.|  
|[CFileDialog::OnItemSelected](../Topic/CFileDialog::OnItemSelected.md)|Aufgerufen, wenn das Containerelement ausgewählt ist.|  
|[CFileDialog::OnLBSelChangedNotify](../Topic/CFileDialog::OnLBSelChangedNotify.md)|Ermöglicht es Ihnen, benutzerdefinierte Aktionen auszuführen, wenn die Datei\-Auswahl ändert.|  
|[CFileDialog::OnShareViolation](../Topic/CFileDialog::OnShareViolation.md)|Handlefreigabenverletzungen.|  
|[CFileDialog::OnTypeChange](../Topic/CFileDialog::OnTypeChange.md)|Bearbeitet die `WM_NOTIFY CDN_TYPECHANGE` Meldung.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFileDialog::m\_ofn](../Topic/CFileDialog::m_ofn.md)|Die Struktur Windows `OPENFILENAME`.  Bietet Zugriff auf den grundlegenden Dateidialogfeldparametern.|  
  
## Hinweise  
 Allgemeine Dateidialogfelder lassen Sie DateiAuswahldialogfelder beispielsweise **Datei öffnen** und **Speichern unter**, in ähnlicher Weise implementieren, das mit Windows\-Standards konsistent ist.  
  
 Sie können [CFileDialog](../../mfc/reference/cfiledialog-class.md) verwenden, wie mit dem bereitgestellten Konstruktor ist, oder eine eigene Dialogfeldklasse von `CFileDialog` ableiten und einen Konstruktor schreiben, um Ihre Anforderungen anpassen.  In beiden Fällen verhalten sich diese Dialogfelder wie Standard\-MFC\-Dialogfelder, da sie von [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md) abgeleitet werden.  `CFileDialog` beruht auf der COMMDLG.DLL\-Datei, die in Windows enthalten ist.  
  
 unterscheiden sich die Darstellung und Funktionalität `CFileDialog` mit [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] aus früheren Versionen von Windows.  Der Standardwert `CFileDialog` verwendet automatisch das neue [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Format ohne Codeänderungen, wenn ein Programm und Ausführung unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] kompiliert wird.  Verwenden Sie den `bVistaStyle`\-Parameter im Konstruktor, um dieses automatische Updates manuell zu überschreiben.  Die Ausnahme zum automatischen Update kann benutzerdefinierte Dialogfelder.  Sie werden nicht in das neue Format konvertiert.  Weitere Informationen über den Konstruktor, finden Sie unter [CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md).  
  
> [!NOTE]
>  Das Steuerelement\-ID\-System unterscheidet sich in [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] aus früheren Versionen von Windows, wenn Sie `CFileDialog` verwenden.  Sie müssen alle Verweise auf `CFileDialog`\-Steuerelemente im Code aktualisieren, bevor Sie das Projekt von einer früheren Version von Windows portieren können.  
  
 Einige `CFileDialog`\-Methoden werden nicht unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] unterstützt.  Überprüfen Sie das einzelne Methodenthema zu Informationen dazu, ob die \- Methode unterstützt wird.  Außerdem sind die folgenden geerbten Funktionen nicht unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] unterstützt:  
  
-   [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)  
  
-   [CDialog::OnSetFont](../Topic/CDialog::OnSetFont.md)  
  
 Die Fenstermeldungen für die `CFileDialog`\-Klasse hängen davon ab, welches Betriebssystem Sie verwenden.  Beispielsweise unterstützen Windows XP nicht [CDialog::OnCancel](../Topic/CDialog::OnCancel.md) und [CDialog::OnOK](../Topic/CDialog::OnOK.md) für die `CFileDialog`\-Klasse.  unterstützt jedoch [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] sie.  Weitere Informationen über die verschiedenen Meldungen, die und die Reihenfolge generiert werden, in der sie empfangen werden, finden Sie unter [CFileDialog\-Beispiel: Protokollierungsereignisreihenfolge](../../top/visual-cpp-samples.md).  
  
 Um ein `CFileDialog`\-Objekt zu verwenden, erstellen Sie zuerst das \- Objekt mit dem `CFileDialog`\-Konstruktor verwenden.  Nachdem das Dialogfeld erstellt wurde, können Sie alle Werte in der [CFileDialog::m\_ofn](../Topic/CFileDialog::m_ofn.md)\-Struktur festlegen oder ändern, um die Werte oder die Bedingungen der Dialogfeld\-Steuerelemente zu initialisieren.  Die `m_ofn`\-Struktur ist vom Typ `OPENFILENAME`.  Weitere Informationen finden Sie unter [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Nachdem Sie die Dialogfeld\-Steuerelemente initialisieren, rufen Sie die [CFileDialog::DoModal](../Topic/CFileDialog::DoModal.md)\-Methode auf, um das Dialogfeld anzuzeigen, sodass der Benutzer den Pfad und den Dateinamen eingeben kann.  `DoModal` gibt zurück, ob der Benutzer das OK \(IDOK\) oder auf die Schaltfläche des Löschvorgangs \(IDCANCEL\) geklickt hat.  Wenn `DoModal` IDOK zurückgibt, können Sie eine der Funktionen `CFileDialog` öffentlichen Members verwenden, um die Informationen abzurufen, die vom Benutzer abgelegt werden.  
  
> [!NOTE]
>  Die [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] verursacht Aufrufe von [IFileDialog::SetFileTypes](http://msdn.microsoft.com/library/windows/desktop/bb775980) einen Fehler.  Der zweite Aufruf von `SetFileTypes` für jede Instanz von `CFileDialog` gibt `E_UNEXPECTED` in [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] zurück.  Einige `CFileDialog`\-Methodenfunktionen rufen `SetFileTypes` auf.  Beispielsweise generiert zwei Aufrufe von `CFileDialog::DoModal` für die gleiche Instanz von `CFileDialog`[ASSERT](../Topic/ASSERT%20\(MFC\).md).  
  
 `CFileDialog` enthält mehrere geschützte Member ein, die Sie benutzerdefinierte Behandlung Freigabenverletzungen, Dateinamenvalidierung und Listenfeldänderungsbenachrichtigung ausführen können.  Diese geschützten Member sind Rückruffunktionen, dass die meisten Anwendungen nicht verwenden müssen, da Standard Behandlung automatisch ausgeführt wird.  Meldungszuordnungseinträge für diese Funktionen sind nicht erforderlich, da sie virtuelle StandardFunktionen sind.  
  
 Sie können die Funktion Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) verwenden, um mehr über den Fehler zu ermitteln, ob ein Fehler aufgetreten ist während der Initialisierung des Dialogfelds und zu erfahren.  
  
 Die `CFileDialog` Zerstörung von Objekten wird automatisch behandelt.  Sie müssen [CDialog::EndDialog](../Topic/CDialog::EndDialog.md) nicht aufrufen.  
  
 Um die ausgewählten mehrere Dateien des Benutzers zu lassen, legen Sie das \- Flag fest `OFN_ALLOWMULTISELECT` bevor Sie `DoModal` aufrufen.  Sie müssen einen eigenen Dateinamenpuffer angeben, um die zurückgegebene Liste mehrerer Dateinamen angepasst.  Führen Sie dies, indem Sie `m_ofn.lpstrFile` mit einem Zeiger auf einen Puffer ersetzen, den Sie zugeordnet haben, nachdem Sie `CFileDialog` erstellen, aber bevor Sie `DoModal` aufrufen.  
  
 Außerdem müssen Sie `m_ofn.nMaxFile` festlegen, indem Sie die Anzahl von Zeichen im Puffer verwenden, der auf durch `m_ofn.lpstrFile` gezeigt wird.  Beim Festlegen der maximalen Anzahl der zu `n` ausgewählt werden, Dateien, die erforderliche Puffergröße `n * (_MAX_PATH + 1) + 1` sind.  Der erste Punkt, der im Puffer zurückgegeben wird, ist der Pfad zum Ordner, in dem die Dateien ausgewählt wurden.  Für eine Dialogfelder [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] sind die Verzeichnis\- und Dateinamenzeichenfolgen, mit einem zusätzlichen NULL\-Zeichen nach dem letzten Dateinamen auf NULL endende.  Dieses Format aktiviert die Explorer\-Formatdialogfelder, um lange Dateinamen zurückzugeben, die Leerzeichen enthalten.  Für alte Dialogfelder werden die Verzeichnis\- und Dateinamenzeichenfolgen durch Leerzeichen getrennt und die Funktion verwendet kurze Dateinamen für Dateinamen mit Leerzeichen.  
  
 Das folgende Beispiel zeigt, wie ein Puffer verwendet, um mehrere Dateinamen abzurufen und anzuzeigen.  
  
 [!CODE [NVC_MFCFiles#23](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCFiles#23)]  
  
 Um die Puffergröße auf den Benutzer zu ändern, der mehrere Dateinamen auswählt, müssen Sie eine neue Klasse von ableiten und die `CFileDialog`[CFileDialog::OnFileNameChange](../Topic/CFileDialog::OnFileNameChange.md)\-Methode überschreiben.  
  
 Wenn Sie eine neue Klasse von `CFileDialog` ableiten, können Sie eine Meldungszuordnung verwenden, um alle Nachrichten zu bearbeiten.  Um die standardmäßige Meldungsbehandlung zu erweitern, leiten Sie eine Klasse von `CFileDialog`, fügen Sie eine Meldungszuordnung der neuen Klasse hinzu, und stellen Sie Memberfunktionen für die neuen Meldungen bereit.  Sie müssen eine Hookfunktion nicht bereitstellen, um das Dialogfeld anzupassen.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFileDialog`, erstellen Sie eine benutzerdefinierte Dialogfeldvorlage, und fügen Sie eine Meldungszuordnung hinzu um die Benachrichtigungsmeldungen aus den erweiterten \- Steuerelementen verarbeiten.  Führen Sie alle nicht verarbeiteten Meldungen an die Basisklasse weiter.  Sie müssen die Hookfunktion nicht anpassen.  
  
 Wenn Sie das [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Format `CFileDialog` verwenden, können Sie Meldungszuordnungen und Dialogfeldvorlagen nicht verwenden.  Stattdessen müssen Sie die COM\-Schnittstellen für ähnliche Funktionen verwenden.  
  
 Weitere Informationen zum Verwenden von `CFileDialog` finden Sie unter [Standarddialogfeld\-Klassen](../../mfc/common-dialog-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFileDialog`  
  
## Anforderungen  
 **Header:** afxdlgs.h  
  
## Siehe auch  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)