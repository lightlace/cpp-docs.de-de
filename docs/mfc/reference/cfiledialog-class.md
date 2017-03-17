---
title: CFileDialog-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileDialog
- AFXDLGS/CFileDialog
- AFXDLGS/CFileDialog::CFileDialog
- AFXDLGS/CFileDialog::AddCheckButton
- AFXDLGS/CFileDialog::AddComboBox
- AFXDLGS/CFileDialog::AddControlItem
- AFXDLGS/CFileDialog::AddEditBox
- AFXDLGS/CFileDialog::AddMenu
- AFXDLGS/CFileDialog::AddPlace
- AFXDLGS/CFileDialog::AddPushButton
- AFXDLGS/CFileDialog::AddRadioButtonList
- AFXDLGS/CFileDialog::AddSeparator
- AFXDLGS/CFileDialog::AddText
- AFXDLGS/CFileDialog::ApplyOFNToShellDialog
- AFXDLGS/CFileDialog::DoModal
- AFXDLGS/CFileDialog::EnableOpenDropDown
- AFXDLGS/CFileDialog::EndVisualGroup
- AFXDLGS/CFileDialog::GetCheckButtonState
- AFXDLGS/CFileDialog::GetControlItemState
- AFXDLGS/CFileDialog::GetControlState
- AFXDLGS/CFileDialog::GetEditBoxText
- AFXDLGS/CFileDialog::GetFileExt
- AFXDLGS/CFileDialog::GetFileName
- AFXDLGS/CFileDialog::GetFileTitle
- AFXDLGS/CFileDialog::GetFolderPath
- AFXDLGS/CFileDialog::GetIFileDialogCustomize
- AFXDLGS/CFileDialog::GetIFileOpenDialog
- AFXDLGS/CFileDialog::GetIFileSaveDialog
- AFXDLGS/CFileDialog::GetNextPathName
- AFXDLGS/CFileDialog::GetOFN
- AFXDLGS/CFileDialog::GetPathName
- AFXDLGS/CFileDialog::GetReadOnlyPref
- AFXDLGS/CFileDialog::GetResult
- AFXDLGS/CFileDialog::GetResults
- AFXDLGS/CFileDialog::GetSelectedControlItem
- AFXDLGS/CFileDialog::GetStartPosition
- AFXDLGS/CFileDialog::HideControl
- AFXDLGS/CFileDialog::IsPickFoldersMode
- AFXDLGS/CFileDialog::MakeProminent
- AFXDLGS/CFileDialog::RemoveControlItem
- AFXDLGS/CFileDialog::SetCheckButtonState
- AFXDLGS/CFileDialog::SetControlItemState
- AFXDLGS/CFileDialog::SetControlItemText
- AFXDLGS/CFileDialog::SetControlLabel
- AFXDLGS/CFileDialog::SetControlState
- AFXDLGS/CFileDialog::SetControlText
- AFXDLGS/CFileDialog::SetDefExt
- AFXDLGS/CFileDialog::SetEditBoxText
- AFXDLGS/CFileDialog::SetProperties
- AFXDLGS/CFileDialog::SetSelectedControlItem
- AFXDLGS/CFileDialog::SetTemplate
- AFXDLGS/CFileDialog::StartVisualGroup
- AFXDLGS/CFileDialog::UpdateOFNFromShellDialog
- AFXDLGS/CFileDialog::OnButtonClicked
- AFXDLGS/CFileDialog::OnCheckButtonToggled
- AFXDLGS/CFileDialog::OnControlActivating
- AFXDLGS/CFileDialog::OnFileNameChange
- AFXDLGS/CFileDialog::OnFileNameOK
- AFXDLGS/CFileDialog::OnFolderChange
- AFXDLGS/CFileDialog::OnInitDone
- AFXDLGS/CFileDialog::OnItemSelected
- AFXDLGS/CFileDialog::OnLBSelChangedNotify
- AFXDLGS/CFileDialog::OnShareViolation
- AFXDLGS/CFileDialog::OnTypeChange
- AFXDLGS/CFileDialog::m_ofn
dev_langs:
- C++
helpviewer_keywords:
- CFileDialog class
- common file dialog boxes
- dialog boxes, common
ms.assetid: fda4fd3c-08b8-4ce0-8e9d-7bab23f8c6c0
caps.latest.revision: 47
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7cde10ee445a719bce6be4167698bd86c46a18c0
ms.lasthandoff: 02/24/2017

---
# <a name="cfiledialog-class"></a>CFileDialog-Klasse
Kapselt das Standarddialogfeld für öffnen oder Datei Speichervorgänge verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFileDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileDialog::CFileDialog](#cfiledialog)|Erstellt ein `CFileDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileDialog::AddCheckButton](#addcheckbutton)|Das Dialogfeld hinzugefügt eine Kontrollkästchen-Schaltfläche.|  
|[CFileDialog::AddComboBox](#addcombobox)|Ein Kombinationsfeld hinzugefügt zum Dialog.|  
|[CFileDialog::AddControlItem](#addcontrolitem)|Ein Container-Steuerelement im Dialogfeld wird ein Element hinzugefügt.|  
|[CFileDialog::AddEditBox](#addeditbox)|Das Dialogfeld hinzugefügt ein Eingabefeld.|  
|[CFileDialog::AddMenu](#addmenu)|Das Dialogfeld hinzugefügt ein Menü.|  
|[CFileDialog::AddPlace](#addplace)|Überladen. Fügt ein Ordner zur Liste der vom Benutzer zum Öffnen oder Speichern von Elementen platziert.|  
|[CFileDialog::AddPushButton](#addpushbutton)|Das Dialogfeld hinzugefügt eine Schaltfläche.|  
|[CFileDialog::AddRadioButtonList](#addradiobuttonlist)|Das Dialogfeld hinzugefügt Optionsgruppe Optionsfeld (auch bekannt als).|  
|[CFileDialog::AddSeparator](#addseparator)|Fügt ein Trennzeichen zum Dialogfeld.|  
|[CFileDialog::AddText](#addtext)|Im Dialogfeld hinzugefügt Text-Inhalt.|  
|[CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog)|Aktualisiert den Status der `CFileDialog` entsprechend den Parameter und die Flags, die in gespeicherten der `m_ofn` Membervariablen gespeichert.|  
|[CFileDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CFileDialog::EnableOpenDropDown](#enableopendropdown)|Aktiviert eine Dropdown-Liste auf die **öffnen** oder **speichern** Schaltfläche im Dialogfeld.|  
|[CFileDialog::EndVisualGroup](#endvisualgroup)|Beendet das Hinzufügen von Elementen zu einer Gruppe im Dialogfeld.|  
|[CFileDialog::GetCheckButtonState](#getcheckbuttonstate)|Ruft den aktuellen Zustand einer Schaltfläche überprüfen (Kontrollkästchen), klicken Sie im Dialogfeld.|  
|[CFileDialog::GetControlItemState](#getcontrolitemstate)|Ruft den aktuellen Status eines Elements in einem Containersteuerelement finden Sie im Dialogfeld ab.|  
|[CFileDialog::GetControlState](#getcontrolstate)|Ruft die aktuelle Sichtbarkeit und der Status eines bestimmten Steuerelements aktiviert.|  
|[CFileDialog::GetEditBoxText](#geteditboxtext)|Ruft den aktuellen Text in einem Bearbeitungssteuerelement.|  
|[CFileDialog::GetFileExt](#getfileext)|Gibt die Erweiterung der ausgewählten Datei zurück.|  
|[CFileDialog::GetFileName](#getfilename)|Gibt den Dateinamen der ausgewählten Datei zurück.|  
|[CFileDialog::GetFileTitle](#getfiletitle)|Gibt den Titel der ausgewählten Datei zurück.|  
|[CFileDialog::GetFolderPath](#getfolderpath)|Ruft den Pfad der aktuell geöffneten Ordner oder des Verzeichnisses für eine Explorer-Style **öffnen** oder **speichern** Standarddialogfeld.|  
|[CFileDialog::GetIFileDialogCustomize](#getifiledialogcustomize)|Ruft den internen COM-Objekt für eine benutzerdefinierte `CFileDialog` Objekt.|  
|[CFileDialog::GetIFileOpenDialog](#getifileopendialog)|Ruft die interne COM-Objekt für ein `CFileDialog` wird, als ein **öffnen** Dateidialogfeld.|  
|[CFileDialog::GetIFileSaveDialog](#getifilesavedialog)|Ruft die interne COM-Objekt für ein `CFileDialog` wird, als ein **speichern** Dateidialogfeld.|  
|[CFileDialog::GetNextPathName](#getnextpathname)|Gibt den vollständigen Pfad der ausgewählten Datei weiter.|  
|[CFileDialog::GetOFN](#getofn)|Ruft die `OPENFILENAME` Struktur der `CFileDialog` Objekt.|  
|[CFileDialog::GetPathName](#getpathname)|Gibt den vollständigen Pfad der ausgewählten Datei zurück.|  
|[CFileDialog::GetReadOnlyPref](#getreadonlypref)|Gibt den schreibgeschützten Status der ausgewählten Datei zurück.|  
|[CFileDialog::GetResult](#getresult)|Ruft die Wahl, die der Benutzer im Dialogfeld vorgenommen.|  
|[CFileDialog::GetResults](#getresults)|Ruft die Auswahl des Benutzers in einem Dialogfeld die Mehrfachauswahl ab.|  
|[CFileDialog::GetSelectedControlItem](#getselectedcontrolitem)|Ruft ein bestimmtes Element aus dem angegebenen Container der Steuerelemente im Dialogfeld ab.|  
|[CFileDialog::GetStartPosition](#getstartposition)|Gibt die Position des ersten Elements der Liste der Dateinamen zurück.|  
|[CFileDialog::HideControl](#hidecontrol)|Blendet das angegebene Steuerelement in einem Explorer-ähnliche **öffnen** oder **speichern** Standarddialogfeld.|  
|[CFileDialog::IsPickFoldersMode](#ispickfoldersmode)|Bestimmt, ob das aktuelle Dialogfeld im ordnerauswahlmodus.|  
|[CFileDialog::MakeProminent](#makeprominent)|Stellen, damit er abhebt ein Steuerelements im Dialogfeld mit anderen hinzugefügten Steuerelemente verglichen.|  
|[CFileDialog::RemoveControlItem](#removecontrolitem)|Entfernt ein Element aus einem Containersteuerelement im Dialogfeld.|  
|[CFileDialog::SetCheckButtonState](#setcheckbuttonstate)|Legt den aktuellen Status einer Kontrollkästchen-Schaltfläche (Kontrollkästchen) im Dialogfeld fest.|  
|[CFileDialog::SetControlItemState](#setcontrolitemstate)|Legt den aktuellen Status eines Elements in einem Containersteuerelement finden Sie im Dialogfeld fest.|  
|[CFileDialog::SetControlItemText](#setcontrolitemtext)|Legt den Text von einem Steuerelement ein Element. Zum Beispiel der Text, der ein Optionsfeld oder ein Element in einem Menü begleitet.|  
|[CFileDialog::SetControlLabel](#setcontrollabel)|Legt den Text eines Steuerelements, z. B. Text der Schaltfläche oder eine Bezeichnung bearbeiten zugeordnet.|  
|[CFileDialog::SetControlState](#setcontrolstate)|Die aktuelle Sichtbarkeit und der Status eines bestimmten Steuerelements aktiviert.|  
|[CFileDialog::SetControlText](#setcontroltext)|Legt den Text für das angegebene Steuerelement in einem Explorer-ähnliche **öffnen** oder **speichern** Standarddialogfeld.|  
|[CFileDialog::SetDefExt](#setdefext)|Legt die standardmäßige Dateinamenerweiterung für ein Explorer-ähnliche **öffnen** oder **speichern** Standarddialogfeld.|  
|[CFileDialog::SetEditBoxText](#seteditboxtext)|Legt den aktuellen Text in einem Bearbeitungssteuerelement.|  
|[CFileDialog::SetProperties](#setproperties)|Bietet einen Eigenschaftenspeicher, der die Standardwerte definiert, die für das zu speichernde Element verwendet werden sollen.|  
|[CFileDialog::SetSelectedControlItem](#setselectedcontrolitem)|Legt den Auswahlzustand eines bestimmten Elements in einer Optionsfeldgruppe oder ein Kombinationsfeld finden Sie im Dialogfeld fest.|  
|[CFileDialog::SetTemplate](#settemplate)|Legt die Dialogfeldvorlage für die `CFileDialog` Objekt.|  
|[CFileDialog::StartVisualGroup](#startvisualgroup)|Deklariert eine optische Gruppe im Dialogfeld. Nachfolgende Aufrufe an jede Methode "add" Hinzufügen dieser Elemente zu dieser Gruppe.|  
|[CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog)|Aktualisiert die Daten aus der `m_ofn` Membervariable entsprechend den aktuellen Status des Dateidialogfelds.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileDialog::OnButtonClicked](#onbuttonclicked)|Wird aufgerufen, wenn die Schaltfläche geklickt wird.|  
|[CFileDialog::OnCheckButtonToggled](#oncheckbuttontoggled)|Wird aufgerufen, wenn das Kontrollkästchen aktiviert/deaktiviert ist.|  
|[CFileDialog::OnControlActivating](#oncontrolactivating)|Wird aufgerufen, wenn das Steuerelement aktiv wird.|  
|[CFileDialog::OnFileNameChange](#onfilenamechange)|Behandelt die `WM_NOTIFY CDN_SELCHANGE` Nachricht.|  
|[CFileDialog::OnFileNameOK](#onfilenameok)|Der im Dialogfeld eingegebene Dateiname wird überprüft.|  
|[CFileDialog::OnFolderChange](#onfolderchange)|Behandelt die `WM_NOTIFY CDN_FOLDERCHANGE` Nachricht.|  
|[CFileDialog::OnInitDone](#oninitdone)|Behandelt die `WM_NOTIFY CDN_INITDONE` Nachricht.|  
|[CFileDialog::OnItemSelected](#onitemselected)|Wird aufgerufen, wenn der Containerelement ausgewählt wird.|  
|[CFileDialog::OnLBSelChangedNotify](#onlbselchangednotify)|Können Sie benutzerdefinierte Aktionen durchzuführen, wenn die Dateiauswahl ändert.|  
|[CFileDialog::OnShareViolation](#onshareviolation)|Handles freigeben Verstöße.|  
|[CFileDialog::OnTypeChange](#ontypechange)|Behandelt die `WM_NOTIFY CDN_TYPECHANGE` Nachricht.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileDialog::m_ofn](#m_ofn)|Windows `OPENFILENAME` Struktur. Bietet Zugriff auf grundlegende Dialogfeld Feld Parameter.|  
  
## <a name="remarks"></a>Hinweise  
 Allgemeine Dateidialogfelder können Sie die Auswahl von Dateien, z. B. Implementierung von Dialogfeldern **geöffnete Datei** und **speichern**, in einer Weise, die Windows-Standards entspricht.  
  
 Sie können `CFileDialog` ist mit dem Konstruktor angegeben oder Sie können eigene Dialogfeldklasse von ableiten `CFileDialog` und einen Konstruktor, um Ihre Bedürfnisse zu schreiben. In beiden Fällen diese Dialogfelder verhält sich wie standardmäßige MFC-Dialogfelder, da sie von abgeleitet sind die [CCommonDialog Klasse](../../mfc/reference/ccommondialog-class.md). `CFileDialog`Abhängig von der COMMDLG. DLL-Datei, die in Windows enthalten ist.  
  
 Die Darstellung und die Funktionalität der `CFileDialog` mit [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] unterscheiden sich von früheren Versionen von Windows. Die Standardeinstellung `CFileDialog` verwendet automatisch den neuen [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Stil ohne Code geändert wird, wenn ein Programm kompiliert wird und die Ausführung unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Verwenden der `bVistaStyle` -Parameter im Konstruktor auf diese automatische Updates manuell zu überschreiben. Die Ausnahme, die die automatische Aktualisierung ist benutzerdefinierte Dialogfelder. Sie werden nicht in das neue Format konvertiert werden. Weitere Informationen zu den Konstruktor, finden Sie unter [CFileDialog::CFileDialog](#cfiledialog).  
  
> [!NOTE]
>  Die Steuerelement-ID-System unterscheidet sich in [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] aus früheren Versionen von Windows bei Verwendung einer `CFileDialog`. Sie müssen alle Verweise auf Aktualisieren `CFileDialog` Steuerelemente im Code, bevor Sie das Projekt von einer früheren Version von Windows Portieren können.  
  
 Einige `CFileDialog` Methoden werden nicht unterstützt, unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Überprüfen Sie die einzelne Methode Thema Informationen, ob die Methode unterstützt wird. Darüber hinaus werden die folgenden geerbten Funktionen nicht unterstützt unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- [CDialog::](../../mfc/reference/cdialog-class.md#oninitdialog)  
  
- [CDialog::OnSetFont](../../mfc/reference/cdialog-class.md#onsetfont)  
  
 Die Windows-Nachrichten für die `CFileDialog` Klasse variieren, je nachdem, auf welches Betriebssystem Sie verwenden. Windows XP unterstützt beispielsweise keine [CDialog::OnCancel](../../mfc/reference/cdialog-class.md#oncancel) und [CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok) für die `CFileDialog` Klasse. Allerdings [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] unterstützt werden. Weitere Informationen über die verschiedenen Nachrichten, die generiert werden und die Reihenfolge, in der sie empfangen werden, finden Sie unter [CFileDialog-Beispiel: Protokollierung Ereignisreihenfolge](../../visual-cpp-samples.md).  
  
 Verwenden einer `CFileDialog` Objekt, erstellen Sie zuerst mithilfe der `CFileDialog` Konstruktor. Nachdem das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [CFileDialog::m_ofn](#m_ofn) Struktur, um die Werte oder Zustände die Dialogfeld-Steuerelemente initialisieren. Die `m_ofn` Struktur ist vom Typ `OPENFILENAME`. Weitere Informationen finden Sie unter der [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Nachdem Sie die Dialogfeld-Steuerelemente initialisieren, rufen Sie die [CFileDialog::DoModal](#domodal) Methode, um das Dialogfeld Feld, damit der Benutzer den Pfad und den Namen eingeben kann. `DoModal`Gibt zurück, ob der Benutzer auf OK (IDOK) oder auf die Schaltfläche Abbrechen (IDCANCEL) geklickt. Wenn `DoModal` gibt IDOK, können Sie eines der `CFileDialog` öffentliche Memberfunktionen zum Abrufen von Informationen in versetzt, durch das der Benutzer.  
  
> [!NOTE]
>  Klicken Sie unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], mehrere Aufrufe [IFileDialog::SetFileTypes](http://msdn.microsoft.com/library/windows/desktop/bb775980) verursacht einen Fehler. Der zweite Aufruf von `SetFileTypes` für jede Instanz einer `CFileDialog` zurück `E_UNEXPECTED` in [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Einige `CFileDialog` Methode-Funktionen rufen `SetFileTypes`. Zum Beispiel zwei Aufrufe von `CFileDialog::DoModal` für dieselbe Instanz von einer `CFileDialog` generiert [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c).  
  
 `CFileDialog`enthält mehrere geschützte Member, mit denen Sie die benutzerdefinierte Behandlung Freigabe Verstöße, Namen Bestätigung und Benachrichtigung zur Änderung des Listenfeldes führen. Diese geschützte Member sind Rückruffunktionen, die meisten Anwendungen nicht verwendet werden, da die Standardbehandlung automatisch ausgeführt wird. Meldungszuordnungseinträge für diese Funktionen sind nicht erforderlich, da sie die standardmäßige virtuelle Funktionen sind.  
  
 Verwenden Sie die Fenster [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) -Funktion zu bestimmen, ob Fehler während der Initialisierung des Dialogfelds und Weitere Informationen zu dem Fehler.  
  
 Die Zerstörung von `CFileDialog` Objekte erfolgt automatisch. Sie müssen keinen Aufrufen [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog).  
  
 Damit den Benutzer mehrere Dateien auswählen können, setzen die `OFN_ALLOWMULTISELECT` flag vor dem Aufruf von `DoModal`. Sie müssen einen eigene Dateinamenpuffer entsprechend die zurückgegebene Liste der mehrere Dateinamen angeben. Ersetzen Sie hierzu `m_ofn.lpstrFile` mit einem Zeiger auf einen Puffer Sie zugeordnet haben, nach der Konstruktion der `CFileDialog`, aber vor dem Aufruf von `DoModal`.  
  
 Darüber hinaus müssen Sie festlegen `m_ofn.nMaxFile` mit der Anzahl von Zeichen im Puffer, die auf `m_ofn.lpstrFile`. Wenn Sie festlegen, dass die maximale Anzahl von Dateien zu ausgewählt werden `n`, ist die erforderliche Puffergröße `n * (_MAX_PATH + 1) + 1`. Das erste Element im Puffer zurückgegeben, ist der Pfad zu dem Ordner, in dem die Dateien ausgewählt wurden. Für [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]-Stil (Dialogfelder), Verzeichnis- und Zeichenfolgen sind Null-terminiert ist, mit einem zusätzlichen Null-Zeichen nach dem letzten Dateinamen. Dieses Format ermöglicht die Explorer-ähnliche Dialogfelder zurückzugebenden lange Dateinamen, die Leerzeichen enthalten. Für im alten Stil Dialogfelder die Verzeichnis- und -Zeichenfolgen werden durch Leerzeichen getrennt und verwendet die Funktion kurze Dateinamen für Dateinamen mit Leerzeichen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie einen Puffer abrufen und die Liste mehrere Dateinamen verwenden.  
  
 [!code-cpp[NVC_MFCFiles&23;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 So ändern die Größe des Puffers in die Antwort an den Benutzer mehrere Dateinamen auswählen, leiten Sie eine neue Klasse von `CFileDialog` und überschreiben die [CFileDialog::OnFileNameChange](#onfilenamechange) Methode.  
  
 Wenn Sie eine neue Klasse von ableiten `CFileDialog`, mithilfe einer Zuordnung Nachricht können Nachrichten zu verarbeiten. Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CFileDialog`, Hinzufügen einer Nachricht Zuordnung zu der neuen Klasse und bieten Memberfunktionen für die neuen Nachrichten. Sie müssen keinen bieten eine Hookfunktion, um das Dialogfeld Anpassen.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFileDialog`, eine benutzerdefinierten Dialogfeldvorlage angeben und eine Zuordnung der Nachricht zum Verarbeiten der Benachrichtigungen von der erweiterten Steuerelemente hinzufügen. Übergeben Sie alle nicht verarbeiteten Nachrichten an die Basisklasse. Sie müssen nicht die Hookfunktion anpassen.  
  
 Bei Verwendung der [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Stil der `CFileDialog`, können keine nachrichtenzuordnungen und Vorlagen für Dialogfelder. Stattdessen müssen Sie die COM-Schnittstellen für ähnliche Funktionalität verwenden.  
  
 Weitere Informationen zur Verwendung von `CFileDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFileDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="addcheckbutton"></a>CFileDialog::AddCheckButton  
 Das Dialogfeld hinzugefügt eine Kontrollkästchen-Schaltfläche.  
  
```  
HRESULT AddCheckButton(
    DWORD dwIDCtl,  
    const CString& strLabel,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID der Schaltfläche mit dem Häkchen, hinzugefügt werden soll.  
  
 `strLabel`  
 Der Name des Kontrollkästchen-Schaltfläche.  
  
 `bChecked`  
 Ein boolescher Wert, der angibt, des aktuellen Zustands der Schaltfläche mit dem Häkchen. `TRUE`Wenn die Option aktiviert ist; `FALSE` andernfalls  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addcombobox"></a>CFileDialog::AddComboBox  
 Ein Kombinationsfeld hinzugefügt zum Dialog.  
  
```  
HRESULT AddComboBox(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Kombinationsfelds hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addcontrolitem"></a>CFileDialog::AddControlItem  
 Ein Container-Steuerelement im Dialogfeld wird ein Element hinzugefügt.  
  
```  
HRESULT AddControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Containersteuerelements, das Element, das hinzugefügt werden soll.  
  
 `dwIDItem`  
 Die ID des Elements.  
  
 `strLabel`  
 Text des Elements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addeditbox"></a>CFileDialog::AddEditBox  
 Das Dialogfeld hinzugefügt ein Eingabefeld.  
  
```  
HRESULT AddEditBox(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Bearbeitungsfelds hinzufügen.  
  
 `strText`  
 Der Name des bearbeiten.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addmenu"></a>CFileDialog::AddMenu  
 Das Dialogfeld hinzugefügt ein Menü.  
  
```  
HRESULT AddMenu(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Menüs hinzufügen.  
  
 `strLabel`  
 Der Name.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addplace"></a>CFileDialog::AddPlace  
 Fügt ein Ordner zur Liste der vom Benutzer zum Öffnen oder Speichern von Elementen platziert.  
  
```  
void AddPlace(
    LPCWSTR lpszFolder,  
    FDAP fdap = FDAP_TOP) throw();

 
void AddPlace(
    IShellItem* psi,  
    FDAP fdap = FDAP_TOP) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFolder`  
 Ein Pfad zu dem Ordner, dem Benutzer zur Verfügung gestellt werden. Dies kann nur ein Ordner sein.  
  
 `fdap`  
 Gibt an, wo der Ordner in der Liste platziert werden.  
  
 `psi`  
 Ein Zeiger auf ein IShellItem, das den Ordner darstellt, der dem Benutzer zur Verfügung gestellt werden. Dies kann nur ein Ordner sein.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addpushbutton"></a>CFileDialog::AddPushButton  
 Das Dialogfeld hinzugefügt eine Schaltfläche.  
  
```  
HRESULT AddPushButton(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID der Schaltfläche hinzufügen.  
  
 `strLabel`  
 Der Name der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addradiobuttonlist"></a>CFileDialog::AddRadioButtonList  
 Das Dialogfeld hinzugefügt Optionsgruppe Optionsfeld (auch bekannt als).  
  
```  
HRESULT AddRadioButtonList(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID der Schaltfläche Optionsgruppe hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addseparator"></a>CFileDialog::AddSeparator  
 Fügt ein Trennzeichen zum Dialogfeld.  
  
```  
HRESULT AddSeparator(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Trennzeichens hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addtext"></a>CFileDialog::AddText  
 Im Dialogfeld hinzugefügt Text.  
  
```  
HRESULT AddText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Texts, hinzugefügt werden soll.  
  
 `strText`  
 Der Textname.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="applyofntoshelldialog"></a>CFileDialog::ApplyOFNToShellDialog  
 Aktualisiert den aktuellen Status der [CFileDialog](../../mfc/reference/cfiledialog-class.md) basierend auf den Werten, die in gespeicherten der `m_ofn` Datenstruktur.  
  
```  
void ApplyOFNToShellDialog();
```  
  
### <a name="remarks"></a>Hinweise  
 In Versionen von Windows vor [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], das Mitglied [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx) -Datenstruktur wurde mit dem Status der fortlaufend synchronisiert die `CFileDialog`. Alle Änderungen an der [M_ofn](#m_ofn) Membervariable sofort in den Zustand des Dialogfelds dargestellt wurden. Änderungen an den Zustand des Dialogfelds sofort aktualisieren Sie außerdem die `m_ofn` Membervariablen gespeichert.  
  
 In [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], die Werte in der `m_ofn` Membervariable und Status der `CFileDialog` sind nicht unbedingt synchronisiert werden. Diese Funktion erzwingt den Status der `CFileDialog` entsprechend aktualisiert werden die `m_ofn` Struktur. Windows ruft diese Funktion automatisch während des [CFileDialog::DoModal](#domodal).  
  
 Weitere Informationen zur Verwendung der `CFileDialog` Klasse unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog).  
  
##  <a name="cfiledialog"></a>CFileDialog::CFileDialog  
 Rufen Sie diese Funktion zum Erstellen einer standardmäßigen Windows-Dateidialogfeld.  
  
```  
explicit CFileDialog(
    BOOL bOpenFileDialog,  
    LPCTSTR lpszDefExt = NULL,  
    LPCTSTR lpszFileName = NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter = NULL,  
    CWnd* pParentWnd = NULL,  
    DWORD dwSize = 0,  
    BOOL bVistaStyle = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bOpenFileDialog`  
 Der Parameter, der angibt, welche Art von Dialogfeld zu erstellen. Legen Sie es auf `TRUE` zum Erstellen einer **Datei öffnen** Dialogfeld. Legen Sie es auf `FALSE` zum Erstellen einer **Datei speichern unter** im Dialogfeld.  
  
 [in] `lpszDefExt`  
 Die Standarddateinamenerweiterung. Wenn der Benutzer keine enthält bekannte Erweiterung (eine, die eine Zuordnung auf dem Computer des Benutzers) in das Feld Dateiname, die Erweiterung angegeben `lpszDefExt` automatisch an den Dateinamen angehängt. Wenn dieser Parameter `NULL`, keine Erweiterung angefügt wird.  
  
 [in] `lpszFileName`  
 Der erste Dateiname, der im Feld Dateiname angezeigt wird. Wenn `NULL`, wird kein Name für die erste Datei angezeigt.  
  
 [in] `dwFlags`  
 Eine Kombination von ein oder mehrere Flags, die Sie verwenden können, um das Dialogfeld Anpassen. Eine Beschreibung dieser Flags finden Sie in der [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn Sie ändern die `m_ofn.Flags` Member-Struktur, die einen bitweise OR-Operator bei Ihren Änderungen verwenden, um das Standardverhalten unverändert zu lassen.  
  
 [in] `lpszFilter`  
 Eine Reihe von Zeichenfolgenpaare, die Filter angeben, können Sie auf die Datei anwenden. Wenn Sie Dateifilter angeben, werden nur die Dateien, die Filterkriterien in der Liste angezeigt. Finden Sie im Abschnitt "Hinweise" für Weitere Informationen zum Arbeiten mit Dateifiltern.  
  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster oder das Besitzer des Dateidialogfelds.  
  
 [in] `dwSize`  
 Die Größe der `OPENFILENAME` Struktur. Dieser Wert hängt von der Version des Betriebssystems ab. MFC verwendet diesen Parameter bestimmen die geeignete Art des Dialogfelds erstellen (beispielsweise neu [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] Dialogfelder anstatt NT4-Dialogfeldern). Die Standardgröße von 0 bedeutet, die der MFC-Code die Größe des richtigen Dialogfeld bestimmt verwenden, basierend auf die Version des Betriebssystems, auf der das Programm ausgeführt wird.  
  
 [in] `bVistaStyle`  
 **Hinweis** dieser Parameter wird in Visual Studio 2008 und höher verfügbar und wird dazu führen, dass das Dialogfeld "neue Formatvorlage" verwendet werden, nur, wenn Sie mit [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] oder höher.  
  
 Der Parameter, der den Stil des Dateidialogfelds angibt. Legen Sie es auf `TRUE` die neuen Dateidialogfelder der Vista-Stil verwenden. Andernfalls wird das alte Format von Dialogfeldern verwendet werden. Finden Sie im Abschnitt "Hinweise" für Weitere Informationen zu unter Vista ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Entweder ein **Datei öffnen** oder **Datei speichern unter** Dialogfeld erstellt wird, abhängig vom Wert der `bOpenFileDialog`.  
  
 Angeben eines Standard-Erweiterung mit `lpszDefExt` Sie erwarten, kann nicht erzeugt werden, da es selten vorhersagbar ist, welche Erweiterungen dateizuordnungen auf dem Computer des Benutzers haben. Wenn Sie mehr Kontrolle über das Anhängen einer Standard-Erweiterung benötigen, leiten Sie eine eigene Klasse von `CFileDialog`, und überschreiben Sie die `CFileDialog::OnFileNameOK` Methode, um eine eigene Behandlung Erweiterung durchzuführen.  
  
 Legen Sie zum Aktivieren des Benutzers zum Auswählen mehrerer Dateien die `OFN_ALLOWMULTISELECT` flag vor dem Aufruf von [DoModal](#domodal). Sie müssen einen eigene Dateinamenpuffer zum Speichern der zurückgegebenen Liste der mehrere Dateinamen angeben. Ersetzen Sie hierzu `m_ofn.lpstrFile` mit einem Zeiger auf einen Puffer Sie zugeordnet haben, nach der Konstruktion der [CFileDialog](../../mfc/reference/cfiledialog-class.md), aber vor dem Aufruf von `DoModal`. Darüber hinaus müssen Sie festlegen `m_ofn.nMaxFile` mit der Anzahl der Zeichen im Puffer auf den `m_ofn.lpstrFile`. Wenn Sie festlegen, dass die maximale Anzahl von Dateien zu ausgewählt werden `n`, ist die erforderliche Puffergröße `n`*(_MAX_PATH + 1) + 1. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCFiles&23;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 Um dem Benutzer ein Explorer-Style-Dialogfeld Größe ändern, indem Sie die Maus oder die Tastatur zu aktivieren, legen die `OFN_ENABLESIZING` Flag. Dieses Flag ist nur erforderlich, wenn Sie einen Hook-Prozedur oder eine benutzerdefinierte Vorlage bereitstellen. Das Flag kann nur mit einer Explorer-Style-Dialogfeld; Dialogfelder im alten Stil können nicht geändert werden.  
  
 Die `lpszFilter` Parameter wird verwendet, um den Typ des Dateinamens zu bestimmen, muss eine Datei in der Liste angezeigt werden. Die erste Zeichenfolge im String-Paar beschreibt den Filter. die zweite Zeichenfolge gibt an, mit der Erweiterung. Mehrere Erweiterungen können durch ein Semikolon (';'-Zeichen) als Trennzeichen angegeben werden. Die Zeichenfolge endet mit zwei ' |' Zeichen, gefolgt von einem `NULL` Zeichen. Sie können auch eine [CString](../../atl-mfc-shared/using-cstring.md) -Objekt für diesen Parameter.  
  
 Z. B. [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] ermöglicht es Benutzern, Dateien öffnen, die Erweiterungen .xlc (Diagramm) oder XLS (Tabelle), unter anderem. Der Filter für Excel kann folgendermaßen geschrieben werden:  
  
 [!code-cpp[NVC_MFCFiles&#24;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_2.cpp)]  
  
 Jedoch aktualisieren, wenn Sie planen, diese Zeichenfolge direkt verwenden die `OPENFILENAME` -Struktur, sollten Sie die Zeichenfolgen mit Null-Zeichen '\0', statt die senkrechten Striche setzen ('| ').  
  
 Die `bVistaStyle` Parameter gilt nur bei Ausführung unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Unter früheren Versionen von Windows wird dieser Parameter ignoriert. Wenn `bVistaStyle` Wert `TRUE`können beim Kompilieren eines Programms mit [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] oder höher, die neue Vista-Formatvorlage **Dateidialogfeld** verwendet werden. Andernfalls den vorherigen MFC-Stil **Dateidialogfeld** verwendet werden.  
  
 Dialogfeldvorlagen werden auf Dialogfeldern basierend auf nicht unterstützt.`bVistaStyle`  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileDialog::DoModal](#domodal).  
  
##  <a name="domodal"></a>CFileDialog::DoModal  
 Rufen Sie diese Funktion, um die Windows-Standarddateidialogfelds angezeigt und ermöglichen den Benutzer Dateien und Verzeichnisse durchsuchen und geben einen Dateinamen ein.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.  
  
 **IDOK** und **IDCANCEL** Konstanten, die angeben, ob der Benutzer auf die Schaltfläche OK oder Abbrechen ausgewählt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Optionen der Datei im Dialogfeld zu initialisieren, indem Sie Mitglieder festlegen möchten die **M_ofn** -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Z. B. Wenn Sie den Benutzer zum Auswählen mehrerer Dateien zulassen möchten, legen die `OFN_ALLOWMULTISELECT` flag vor dem Aufruf von `DoModal`, wie im Codebeispiel in diesem Thema dargestellt.  
  
 Der Benutzer klickt auf des Dialogfelds OK oder Abbrechen geklickt oder wählt das Schließen über des Dialogfelds option Menü steuern möchten, wird die Steuerung an Ihre Anwendung zurückgegeben. Sie können dann andere Memberfunktionen zum Abrufen der Einstellungen oder die Informationen der Benutzereingaben in das Dialogfeld aufrufen.  
  
 `DoModal`ist eine virtuelle Funktion, die von einer Klasse überschrieben, `CDialog`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#25;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_3.cpp)]  
  
##  <a name="enableopendropdown"></a>CFileDialog::EnableOpenDropDown  
 Ermöglicht eine Dropdownliste öffnen oder Speichern der Schaltfläche im Dialogfeld.  
  
```  
HRESULT EnableOpenDropDown(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID der Dropdown-Liste.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="endvisualgroup"></a>CFileDialog::EndVisualGroup  
 Beendet das Hinzufügen von Elementen zu einer Gruppe im Dialogfeld.  
  
```  
HRESULT EndVisualGroup();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn erfolgreich. ein Fehlerwert andernfalls.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcheckbuttonstate"></a>CFileDialog::GetCheckButtonState  
 Ruft den aktuellen Zustand einer Schaltfläche überprüfen (Kontrollkästchen), klicken Sie im Dialogfeld ab.  
  
```  
HRESULT GetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL& bChecked);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Kontrollkästchens.  
  
 `bChecked`  
 Der Status des Kontrollkästchens. `TRUE`weist darauf hin überprüft. `FALSE` gibt deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcontrolitemstate"></a>CFileDialog::GetControlItemState  
 Ruft den aktuellen Status eines Elements in einem Containersteuerelement finden Sie im Dialogfeld ab.  
  
```  
HRESULT GetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Containersteuerelements.  
  
 `dwIDItem`  
 Die ID des Elements.  
  
 `dwState`  
 Ein Verweis auf eine Variable, die eine weitere Werte aus der Enumeration CDCONTROLSTATE empfängt, der den aktuellen Zustand des Steuerelements angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcontrolstate"></a>CFileDialog::GetControlState  
 Ruft die aktuelle Sichtbarkeit und der Status eines bestimmten Steuerelements aktiviert.  
  
```  
HRESULT GetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Steuerelements.  
  
 `dwState`  
 Ein Verweis auf eine Variable, die ein oder mehrere Werte aus der Enumeration CDCONTROLSTATE empfängt, der den aktuellen Zustand des Steuerelements angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="geteditboxtext"></a>CFileDialog::GetEditBoxText  
 Ruft den aktuellen Text in einem Bearbeitungssteuerelement.  
  
```  
HRESULT GetEditBoxText(
    DWORD dwIDCtl,  
    CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Bearbeitungsfelds.  
  
 `strText`  
 Der Textwert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getfileext"></a>CFileDialog::GetFileExt  
 Rufen Sie diese Funktion rufen Sie die Erweiterung des Dateinamens in das Dialogfeld eingegeben haben.  
  
```  
CString GetFileExt() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Erweiterung des Dateinamens.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Name der Datei eingetragen ist z. B. Daten auf. TXT, `GetFileExt` "TXT" zurückgegeben.  
  
 Wenn `m_ofn.Flags` hat die `OFN_ALLOWMULTISELECT` Flags gesetzt werden, diese Zeichenfolge enthält eine Abfolge von Null-terminierte Zeichenfolgen, wobei die erste Zeichenfolge, die den Verzeichnispfad der Dateigruppe ausgewählt, wird gefolgt von den Namen aller Dateien, die vom Benutzer ausgewählt. Verwenden Sie zum Abrufen der Dateipfadnamen der [GetStartPosition](#getstartposition) und [GetNextPathName](#getnextpathname) Memberfunktionen.  
  
##  <a name="getfilename"></a>CFileDialog::GetFileName  
 Rufen Sie diese Funktion, um den Namen der im Dialogfeld eingegebene Dateiname abzurufen.  
  
```  
CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Der Name der Datei enthält sowohl das Präfix als auch die Erweiterung. Z. B. `GetFileName` zurück "TEXT. DAT"für die Datei C:\FILES\TEXT.DAT.  
  
 Wenn `m_ofn.Flags` hat die `OFN_ALLOWMULTISELECT` -flag festgelegt ist, rufen Sie [GetStartPosition](#getstartposition) und [GetNextPathName](#getnextpathname) ein Pfadname abgerufen.  
  
##  <a name="getfiletitle"></a>CFileDialog::GetFileTitle  
 Rufen Sie diese Funktion zum Abrufen des Titels der Datei im Dialogfeld eingegeben haben.  
  
```  
CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Titel der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Der Titel der Datei enthält nur ein Präfix, ohne den Pfad oder die Erweiterung. Z. B. `GetFileTitle` "TEXT" für die Datei C:\FILES\TEXT.DAT zurück.  
  
 Wenn `m_ofn.Flags` hat die `OFN_ALLOWMULTISELECT` Flags gesetzt werden, diese Zeichenfolge enthält eine Abfolge von Null-terminierte Zeichenfolgen, wobei die erste Zeichenfolge, die den Verzeichnispfad der Dateigruppe ausgewählt, wird gefolgt von den Namen aller Dateien, die vom Benutzer ausgewählt. Aus diesem Grund verwenden Sie die [GetStartPosition](#getstartposition) und [GetNextPathName](#getnextpathname) Memberfunktionen zum Abrufen des nächsten Dateinamens in der Liste.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileDialog::DoModal](#domodal).  
  
##  <a name="getfolderpath"></a>CFileDialog::GetFolderPath  
 Rufen Sie diese Memberfunktion um den Pfad der aktuell geöffneten Ordner oder des Verzeichnisses für eine Explorer-Style öffnen oder Speichern unter Standarddialogfeld abzurufen.  
  
```  
CString GetFolderPath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das dem aktuell geöffneten Ordner oder Verzeichnis enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld muss mit erstellt wurden die **OFN_EXPLORER** formatieren, andernfalls schlägt die Methode mit einer Assertion auszuführen.  
  
 Sie können diese Methode aufrufen, nur verwendet werden, während das Dialogfeld angezeigt wird. Nachdem das Dialogfeld geschlossen wurde, diese Funktion funktioniert nicht mehr, und die Methode mit einer Assertion fehl.  
  
##  <a name="getifiledialogcustomize"></a>CFileDialog::GetIFileDialogCustomize  
 Ruft einen Zeiger auf die interne COM-Objekt für einen bestimmten [CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
```  
IFileDialogCustomize* GetIFileDialogCustomize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger auf die interne COM-Objekt für die `CFileDialog`. Es obliegt der this-Zeiger entsprechend freigeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion nur unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] mit einem Objekt mit `bVistaStyle` festgelegt `true`. Wenn Sie diese Funktion verwenden, wenn `bVistaStyle` ist `false`, wird zurückgegeben, `NULL` im Releasemodus und löst eine Assertion im Debugmodus.  
  
 Weitere Informationen zu den `IFileDialogCustomize` Benutzeroberfläche, siehe [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912).  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird das interne COM-Objekt. Um dieses Codebeispiel ausführen zu können, müssen Sie es unter Kompilieren [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog&4;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_4.cpp)]  
  
##  <a name="getifileopendialog"></a>CFileDialog::GetIFileOpenDialog  
 Ruft einen Zeiger auf die interne COM-Objekt für einen bestimmten `CFileDialog`.  
  
```  
IFileOpenDialog* GetIFileOpenDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger auf die interne COM-Objekt für die `CFileDialog`. Es obliegt der this-Zeiger entsprechend freigeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion nur unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] mit einem Objekt mit `bVistaStyle` festgelegt `true`. Diese Funktion gibt `NULL` Wenn die `CFileDialog` ist ein **öffnen** im Dialogfeld oder, wenn `bVistaStyle` auf festgelegt ist `false`. In diesem letzten Fall gibt die Funktion nur `NULL` im Releasemodus - im Debugmodus löst es eine Assertion.  
  
 Weitere Informationen zu den `IFileOpenDialog` Benutzeroberfläche, siehe [IFileOpenDialog](http://msdn.microsoft.com/library/windows/desktop/bb775834).  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird das interne COM-Objekt. Um diesen Code auszuführen, müssen Sie es unter Kompilieren [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog&#2;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_5.cpp)]  
  
##  <a name="getifilesavedialog"></a>CFileDialog::GetIFileSaveDialog  
 Ruft einen Zeiger auf die interne COM-Objekt für einen bestimmten `CFileDialog`.  
  
```  
IFileSaveDialog* GetIFileSaveDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger auf die interne COM-Objekt für die `CFileDialog`. Es obliegt der this-Zeiger entsprechend freigeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion nur unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] mit einem Objekt mit `bVistaStyle` festgelegt `true`. Diese Funktion zurück `NULL` Wenn der `CFileDialog` ist ein **speichern** Dialogfeld oder, wenn `bVistaStyle` auf festgelegt ist `false`. In diesem letzten Fall gibt die Funktion nur `NULL` im Releasemodus - im Debugmodus löst es eine Assertion.  
  
 Weitere Informationen zu den `IFileSaveDialog` Benutzeroberfläche, siehe [IFileSaveDialog](http://msdn.microsoft.com/library/windows/desktop/bb775688).  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird das interne COM-Objekt. Um dieses Codebeispiel ausführen zu können, müssen Sie es unter Kompilieren [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog&3;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_6.cpp)]  
  
##  <a name="getnextpathname"></a>CFileDialog::GetNextPathName  
 Rufen Sie diese Funktion zum Abrufen der nächsten Dateinamens aus der Gruppe im Dialogfeld ausgewählt.  
  
```  
CString GetNextPathName(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNextPathName` oder `GetStartPosition` -Funktionsaufruf. **NULL** , wenn das Ende der Liste erreicht wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vollständige Pfad der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Der Pfad des Dateinamens enthält den Titel der Datei sowie den gesamten Pfad. Z. B. `GetNextPathName` zurück "C:\FILES\TEXT. DAT"für die Datei C:\FILES\TEXT.DAT. Sie können `GetNextPathName` in einer Iterationsschleife forward, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetStartPosition`.  
  
 Wenn die Auswahl aus nur einer Datei besteht, wird dem Dateinamen zurückgegeben.  
  
##  <a name="getofn"></a>CFileDialog::GetOFN  
 Ruft die zugeordnete **OPENFILENAME** Struktur.  
  
```  
const OPENFILENAME& GetOFN() const;  
  
OPENFILENAME& GetOFN();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Version dieser Funktion verwenden, um die Darstellung zu initialisieren eine **Datei öffnen** oder **Datei speichern unter** Dialogfeld, sobald es erstellt wurde, jedoch vor der Anzeige mit der `DoModal` Member-Funktion. Sie können z. B. Festlegen der **LpstrTitle** Mitglied **M_ofn** die Beschriftung im Dialogfeld haben soll.  
  
##  <a name="getpathname"></a>CFileDialog::GetPathName  
 Rufen Sie diese Funktion zum Abrufen des vollständigen Pfads der Datei im Dialogfeld eingegeben haben.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vollständige Pfad der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Der Pfad des Dateinamens enthält den Titel der Datei sowie den gesamten Pfad. Z. B. `GetPathName` zurück "C:\FILES\TEXT. DAT"für die Datei C:\FILES\TEXT.DAT.  
  
 Wenn `m_ofn.Flags` hat die `OFN_ALLOWMULTISELECT` Flags gesetzt werden, diese Zeichenfolge enthält eine Sequenz von Null-Teminated gefolgt Zeichenfolgen, wobei die erste Zeichenfolge, die den Verzeichnispfad der Dateigruppe ausgewählt haben, werden die Namen aller Dateien, die vom Benutzer ausgewählt. Aus diesem Grund verwenden Sie die [GetStartPosition](#getstartposition) und [GetNextPathName](#getnextpathname) Memberfunktionen zum Abrufen des nächsten Dateinamens in der Liste.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileDialog::DoModal](#domodal).  
  
##  <a name="getreadonlypref"></a>CFileDialog::GetReadOnlyPref  
 Rufen Sie diese Funktion, um zu bestimmen, ob das Kontrollkästchen schreibgeschützt in der Windows-Datei öffnen und Datei speichern unter Standarddialogfelder ausgewählt wurde.  
  
```  
BOOL GetReadOnlyPref() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Sie im Dialogfeld das Kontrollkästchen Schreibgeschützt aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Kontrollkästchen schreibgeschützt ausblenden, indem Sie die Einstellung der `OFN_HIDEREADONLY` im Stil der `CFileDialog` Konstruktor.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]Stil `CFileDialog` Objekte unterstützen diese Funktion nicht. Bei dem Versuch, diese Funktion zu verwenden, auf eine [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Stil `CFileDialog` löst [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).   
  
##  <a name="getresult"></a>CFileDialog::GetResult  
 Ruft die Wahl, die der Benutzer im Dialogfeld vorgenommen.  
  
```  
IShellItem* GetResult() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein IShellItem, die die Auswahl des Benutzers darstellt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getresults"></a>CFileDialog::GetResults  
 Ruft die Benutzerauswahl in einem Dialogfeld, die Auswahl mehrerer Elemente ermöglicht.  
  
```  
IShellItemArray* GetResults() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine IShellItemArray über die im Dialogfeld ausgewählten Elemente zugegriffen werden können.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getselectedcontrolitem"></a>CFileDialog::GetSelectedControlItem  
 Ruft ein bestimmtes Element aus dem angegebenen Container-Steuerelement im Dialogfeld ab.  
  
```  
HRESULT GetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD& dwIDItem);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Containersteuerelements.  
  
 `dwIDItem`  
 Die ID des Elements, das der Benutzer im Steuerelement ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getstartposition"></a>CFileDialog::GetStartPosition  
 Rufen Sie diese Memberfunktion, um die Position des ersten Dateipfadnamens in der Liste abzurufen, wenn `m_ofn.Flags` hat die `OFN_ALLOWMULTISELECT` flag festgelegt.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration verwendet werden kann **NULL** , wenn die Liste leer ist.  
  
##  <a name="hidecontrol"></a>CFileDialog::HideControl  
 Rufen Sie diese Memberfunktion, um das angegebene Steuerelement in einem Explorer-Style öffnen oder Speichern unter Allgemeine Dialogfeld auszublenden.  
  
```  
void HideControl(int nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Die ID des Steuerelements ausgeblendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld muss mit erstellt wurden die **OFN_EXPLORER** formatieren, andernfalls schlägt die Funktion mit einer Assertion fehl.  
  
##  <a name="ispickfoldersmode"></a>CFileDialog::IsPickFoldersMode  
 Bestimmt, ob das aktuelle Dialogfeld im ordnerauswahlmodus.  
  
```  
BOOL IsPickFoldersMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Dialogfeld in ordnerauswahlmodus ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_ofn"></a>CFileDialog::m_ofn  
 `m_ofn`ist eine Struktur vom Typ `OPENFILENAME`. Die Daten in dieser Struktur stellt den aktuellen Zustand des der `CFileDialog`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Struktur, um die Darstellung der Initialisieren einer **Datei öffnen** oder **Datei speichern unter** Dialogfeld, nachdem Sie es erstellt, jedoch bevor Sie es mit Anzeigen der [DoModal](#domodal) Methode. Sie können z. B. Festlegen der `lpstrTitle` Mitglied `m_ofn` die Beschriftung im Dialogfeld haben soll.  
  
 Mit der [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Stil der [CFileDialog](../../mfc/reference/cfiledialog-class.md), `m_ofn` ist nicht gewährleistet, dass den Status des Dialogfelds immer übereinstimmen. Es wird das Dialogfeld in früheren Versionen von Windows synchronisiert werden. Finden Sie unter [CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog) und [CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog) für Weitere Informationen zum Synchronisieren der `m_ofn` Struktur und die `CFileDialog` Status unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]Stil Dateidialogfelder unterstützen keine bestimmte Elemente und die Flags der `CFileDialog`. Daher haben diese keine Wirkung.  
  
 Im folgenden ist eine Liste der Elemente, die nicht von unterstützt werden [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- `lpstrCustomFilter`  
  
- `lpstrInitialDir`  
  
- `lCustData`  
  
- `lpfnHook`  
  
- `lpTemplateName`  
  
 Die folgenden Flags werden nicht unterstützt und daher wirken sich nicht bei Verwendung der [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Stil der `CFileDialog`:  
  
-   OFN_ENABLEHOOK  
  
-   OFN_ENABLEINCLUDENOTIFY  
  
-   OFN_ENABLETEMPLATE  
  
-   OFN_ENABLETEMPLATEHANDLE  
  
-   OFN_EXPLORER  
  
-   OFN_EXTENSIONDIFFERENT  
  
-   OFN_HIDEREADONLY  
  
-   OFN_LONGNAMES - effektiv immer auf in[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NOLONGNAMES - off effektiv immer im[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NONETWORKBUTTON - effektiv immer auf in[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_READONLY  
  
-   OFN_SHOWHELP  
  
 Weitere Informationen zu dieser Struktur finden Sie unter der [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="makeprominent"></a>CFileDialog::MakeProminent  
 Stellen, damit er abhebt ein Steuerelement im Dialogfeld für andere Steuerelemente verglichen.  
  
```  
HRESULT MakeProminent(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onbuttonclicked"></a>CFileDialog::OnButtonClicked  
 Wird aufgerufen, wenn die Schaltfläche geklickt wird.  
  
```  
virtual void OnButtonClicked(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncheckbuttontoggled"></a>CFileDialog::OnCheckButtonToggled  
 Wird aufgerufen, wenn das Kontrollkästchen aktiviert oder deaktiviert ist.  
  
```  
virtual void OnCheckButtonToggled(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Kontrollkästchens.  
  
 `bChecked`  
 Aktiviert oder deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncontrolactivating"></a>CFileDialog::OnControlActivating  
 Wird aufgerufen, wenn das Steuerelement aktiviert ist.  
  
```  
virtual void OnControlActivating(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onfilenamechange"></a>CFileDialog::OnFileNameChange  
 Wenn Sie behandeln möchten, überschreiben Sie diese Methode die `WM_NOTIFY``CDN_SELCHANGE` Nachricht.  
  
```  
virtual void OnFileNameChange();
```  
  
### <a name="remarks"></a>Hinweise  
 Sendet das System die `CDN_SELCHANGE` angezeigt wird, wenn der Benutzer eine neue Datei oder einen Ordner in der Liste der wählt die **öffnen** oder **speichern unter** im Dialogfeld. Überschreiben Sie diese Methode, wenn Sie alle Aktionen in Antwort auf diese Nachricht ausführen möchten.  
  
 Das System sendet diese Nachricht nur, wenn das Dialogfeld mit dem OFN_EXPLORER-Flag aktiviert erstellt wurde. Weitere Informationen über die Benachrichtigung finden Sie unter [CDN_SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646865). Informationen über das OFN_EXPLORER-Flag finden Sie unter der [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) Struktur und [öffnen und speichern als Dialogfelder](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="onfilenameok"></a>CFileDialog::OnFileNameOK  
 Überschreiben Sie diese Funktion nur, wenn benutzerdefinierte Validierung der Dateien zur Verfügung stellen, die in einem Standarddialogfeld Datei eingegeben werden.  
  
```  
virtual BOOL OnFileNameOK();
```  
  
### <a name="return-value"></a>Rückgabewert  
 1, wenn der Dateiname nicht um einen gültigen Dateinamen ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen Dateinamen anwendungsspezifischen Gründen ablehnen. In der Regel müssen Sie nicht diese Funktion zu verwenden, da das Framework bietet eine Standard-Validierung von Dateinamen und zeigt ein Meldungsfeld an, wenn ein ungültiger Dateiname eingegeben wird.  
  
 Wenn 1 zurückgegeben wird, bleibt das Dialogfeld für den Benutzer zur Eingabe von einem anderen Dateinamen angezeigt. Das Dialogfeld Verfahren schließt das Dialogfeld ist der Rückgabewert 0. Andere ungleich NULL zurückgeben, Werte sind derzeit reserviert und sollte nicht verwendet werden.  
  
##  <a name="onfolderchange"></a>CFileDialog::OnFolderChange  
 Überschreiben Sie diese Funktion behandelt die **WM_NOTIFYCDN_FOLDERCHANGE** Nachricht.  
  
```  
virtual void OnFolderChange();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Benachrichtigung wird gesendet, wenn Sie ein neuer Ordner im Dialogfeld Öffnen oder Speichern unter geöffnet wird.  
  
 Die Benachrichtigung wird nur dann, wenn das Dialogfeld mit den OFN_EXPLORER-Stil erstellt wurde. Weitere Informationen über die Benachrichtigung finden Sie unter [CDN_FOLDERCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646859). Informationen über das OFN_EXPLORER-Format finden Sie unter der [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) Struktur und [öffnen und speichern als Dialogfelder](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="oninitdone"></a>CFileDialog::OnInitDone  
 Überschreiben Sie diese Funktion behandelt die `WM_NOTIFY``CDN_INITDONE` Nachricht.  
  
```  
virtual void OnInitDone();
```  
  
### <a name="remarks"></a>Hinweise  
 Sendet das System diese Benachrichtigung des Systems Abschluss Anordnen von Steuerelementen in der **öffnen** oder **speichern unter** im Dialogfeld für die Steuerelemente im Dialogfeld untergeordneten Platz zu machen.  
  
 Das System sendet dies nur, wenn das Dialogfeld mit den OFN_EXPLORER-Stil erstellt wurde. Weitere Informationen über die Benachrichtigung finden Sie unter [CDN_INITDONE](http://msdn.microsoft.com/library/windows/desktop/ms646863). Informationen über das OFN_EXPLORER-Format finden Sie unter der [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) Struktur und [öffnen und speichern als Dialogfelder](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]Stil Dateidialogfelder unterstützen diese Funktion nicht. Bei dem Versuch, diese Funktion zu verwenden, auf eine [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Stil Dateidialogfeld löst [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md). 
  
##  <a name="onitemselected"></a>CFileDialog::OnItemSelected  
 Wird aufgerufen, wenn das Containerelement ausgewählt ist.  
  
```  
virtual void OnItemSelected(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Containersteuerelements.  
  
 `dwIDItem`  
 Die ID des Elements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbselchangednotify"></a>CFileDialog::OnLBSelChangedNotify  
 Diese Funktion wird aufgerufen, wenn die aktuelle Auswahl in einem Listenfeld geändert wird.  
  
```  
virtual void OnLBSelChangedNotify(
    UINT nIDBox,  
    UINT iCurSel,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDBox*  
 Die ID des im Listenfeld oder Kombinationsfeld, in dem die Markierung auftrat.  
  
 `iCurSel`  
 Der Index der aktuellen Auswahl.  
  
 `nCode`  
 Der Code für den Steuerelement-Benachrichtigung. Dieser Parameter muss einen der folgenden Werte aufweisen:  
  
- **CD_LBSELCHANGE** gibt `iCurSel` das ausgewählte Element in einem Mehrfachauswahl-Listenfeld.  
  
- **CD_LBSELSUB** gibt an, dass `iCurSel` nicht mehr in einem Mehrfachauswahl-Listenfeld ausgewählt ist.  
  
- **CD_LBSELADD** gibt an, dass `iCurSel` in einem Mehrfachauswahl-Listenfeld ausgewählt ist.  
  
- **CD_LBSELNOITEMS** gibt, die in einem Mehrfachauswahl-Listenfeld keine Auswahl vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die benutzerdefinierte Behandlung von Änderungen der Auswahl im Listenfeld bereitzustellen. Angenommen, Sie können diese Funktion verwenden, um die Zugriffsrechte anzuzeigen oder Datum-Last-modified aller Dateien der Benutzer auswählt.  
  
##  <a name="onshareviolation"></a>CFileDialog::OnShareViolation  
 Überschreiben Sie diese Funktion, um die benutzerdefinierte Behandlung Verstöße gegen die Dateifreigabe bereitzustellen.  
  
```  
virtual UINT OnShareViolation(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPathName`  
 Der Pfad der Datei auf der Freigabe verletzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- **OFN_SHAREFALLTHROUGH** der Dateinamen aus dem Dialogfeld zurückgegeben wird.  
  
- **OFN_SHARENOWARN** keine weitere Aktion erforderlich.  
  
- **OFN_SHAREWARN** erhält der Benutzer die standard Warnmeldung für diesen Fehler.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel müssen Sie nicht diese Funktion zu verwenden, da das Framework stellt Überprüfung Verstöße gegen die Freigabe und zeigt ein Meldungsfeld an, wenn eine Freigabe-Verletzung auftritt.  
  
 Wenn Sie die Freigabe Verstoß Überprüfung deaktivieren möchten, verwenden Sie bitweisen OR-Operator kombiniert das Flag **OFN_SHAREAWARE** mit `m_ofn.Flags`.  
  
##  <a name="ontypechange"></a>CFileDialog::OnTypeChange  
 Überschreiben Sie diese Funktion behandelt die **WM_NOTIFYCDN_TYPECHANGE** Nachricht.  
  
```  
virtual void OnTypeChange();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Benachrichtigung wird gesendet, wenn der Benutzer einen neuen Dateityp aus der Liste der Dateitypen öffnen oder im Dialogfeld Speichern unter auswählt.  
  
 Die Benachrichtigung wird nur dann, wenn das Dialogfeld mit den OFN_EXPLORER-Stil erstellt wurde. Weitere Informationen über die Benachrichtigung finden Sie unter [CDN_TYPECHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646868). Informationen über das OFN_EXPLORER-Format finden Sie unter der [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) Struktur und [öffnen und speichern als Dialogfelder](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="removecontrolitem"></a>CFileDialog::RemoveControlItem  
 Entfernt ein Element aus einem Containersteuerelement im Dialogfeld.  
  
```  
HRESULT RemoveControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Containersteuerelements zu entfernen.  
  
 `dwIDItem`  
 Die ID des Elements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcheckbuttonstate"></a>CFileDialog::SetCheckButtonState  
 Legt den aktuellen Status einer Kontrollkästchen-Schaltfläche (Kontrollkästchen) im Dialogfeld fest.  
  
```  
HRESULT SetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Kontrollkästchens.  
  
 `bChecked`  
 Der Status des Kontrollkästchens. `TRUE`weist darauf hin überprüft. `FALSE` deaktiviert angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcontrolitemstate"></a>CFileDialog::SetControlItemState  
 Legt den aktuellen Status eines Elements in einem Containersteuerelement finden Sie im Dialogfeld fest.  
  
```  
HRESULT SetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Containersteuerelements.  
  
 `dwIDItem`  
 Die ID des Elements.  
  
 `dwState`  
 Ein oder mehrere Werte aus der CDCONTROLSTATE-Enumeration, die den neuen Zustand des Steuerelements angeben.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcontrolitemtext"></a>CFileDialog::SetControlItemText  
 Legt den Text von einem Steuerelement ein Element. Zum Beispiel der Text, der ein Optionsfeld oder ein Element in einem Menü begleitet.  
  
```  
HRESULT SetControlItemText(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Containersteuerelements.  
  
 `dwIDItem`  
 Die ID des Elements.  
  
 `strLabel`  
 Text des Elements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcontrollabel"></a>CFileDialog::SetControlLabel  
 Legt den Text eines Steuerelements, z. B. Text der Schaltfläche oder eine Bezeichnung bearbeiten zugeordnet.  
  
```  
HRESULT SetControlLabel(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Steuerelements.  
  
 `strLabel`  
 Der Name des Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcontrolstate"></a>CFileDialog::SetControlState  
 Die aktuelle Sichtbarkeit und der Status eines bestimmten Steuerelements aktiviert.  
  
```  
HRESULT SetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Steuerelements.  
  
 `dwState`  
 Ein oder mehrere Werte aus der CDCONTROLSTATE-Enumeration, die den aktuellen Zustand des Steuerelements an.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcontroltext"></a>CFileDialog::SetControlText  
 Rufen Sie diese Methode, wenn den Text für das angegebene Steuerelement in einem Explorer-Style **öffnen** oder **speichern** das Dialogfeld.  
  
```  
void SetControlText(
    int nID,  
    LPCSTR lpsz);

 
void SetControlText(
    int nID,  
    const wchar_t *lpsz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die ID des Steuerelements für den Text festgelegt.  
  
 [in] `lpsz`  
 Ein Zeiger auf die Zeichenfolge mit dem Text für das Steuerelement festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Beide Versionen dieser Funktion gelten, die Unicode verwenden. Nur die Version mit dem Typ LPCSTR ist jedoch gültig für Anwendungen, [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)].  
  
 Um diese Methode verwenden, müssen Sie das Dialogfeld mit dem OFN_EXPLORER-Stil erstellen. Andernfalls schlägt die Funktion mit einer Assertion fehl.  
  
##  <a name="setdefext"></a>CFileDialog::SetDefExt  
 Rufen Sie diese Funktion, um die standardmäßige Dateinamenerweiterung für ein Explorer-Style öffnen oder Speichern unter Standarddialogfeld festgelegt.  
  
```  
void SetDefExt(LPCSTR lpsz);
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Ein Zeiger auf eine Zeichenfolge mit der Standard für die Dialogfeldobjekt verwenden. Diese Zeichenfolge muss nicht auf einen Punkt (.) enthalten.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld muss mit erstellt wurden die **OFN_EXPLORER** formatieren, andernfalls schlägt die Funktion mit einer Assertion fehl.  
  
##  <a name="seteditboxtext"></a>CFileDialog::SetEditBoxText  
 Legt den aktuellen Text in einem Bearbeitungssteuerelement.  
  
```  
HRESULT SetEditBoxText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Bearbeitungsfelds.  
  
 `strText`  
 Der Textwert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setproperties"></a>CFileDialog::SetProperties  
 Bietet einen Eigenschaftenspeicher, der die Standardwerte definiert, die für das zu speichernde Element verwendet werden sollen.  
  
```  
BOOL SetProperties(LPCWSTR lpszPropList);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPropList`  
 Eine Liste der vordefinierten Eigenschaften, die durch ein ";" voneinander getrennt sind. Eine Liste der Flags finden Sie in der `Flags` Abschnitt [OPENFILENAME](http://msdn.microsoft.com/en-us/8cecfd45-f7c1-4f8d-81a0-4e7fecc3b104).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setselectedcontrolitem"></a>CFileDialog::SetSelectedControlItem  
 Legt den Auswahlzustand eines bestimmten Elements in einer Optionsfeldgruppe oder ein Kombinationsfeld finden Sie im Dialogfeld fest.  
  
```  
HRESULT SetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID des Containersteuerelements.  
  
 `dwIDItem`  
 Die ID des Elements, das der Benutzer im Steuerelement ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settemplate"></a>CFileDialog::SetTemplate  
 Legt die Dialogfeldvorlage für die [CFileDialog](../../mfc/reference/cfiledialog-class.md) Objekt.  
  
```  
void SetTemplate(
    UINT nWin3ID,  
    UINT nWin4ID);

 
void SetTemplate(
    LPCTSTR lpWin3ID,  
    LPCTSTR lpWin4ID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nWin3ID`  
 Enthält die ID-Nummer der Dialogfeldvorlagen-Ressource für den Explorer `CFileDialog` Objekt. Diese Vorlage wird nur verwendet, unter Windows NT 3.51 oder der OFN_EXPLORER-Stil nicht vorhanden ist.  
  
 [in] `nWin4ID`  
 Enthält die ID-Nummer der Dialogfeldvorlagen-Ressource für den Explorer `CFileDialog` Objekt. Diese Vorlage dient nur für [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] und höher, Windows 95 und höher, oder wenn der Stil OFN_EXPLORER vorhanden ist.  
  
 [in] `lpWin3ID`  
 Enthält den Namen der Dialogfeldvorlagen-Ressource für den Explorer `CFileDialog` Objekt. Diese Vorlage wird nur verwendet, unter Windows NT 3.51 oder der OFN_EXPLORER-Stil nicht vorhanden ist.  
  
 [in] `lpWin4ID`  
 Enthält den Namen der Dialogfeldvorlagen-Ressource im Explorer `CFileDialog` Objekt. Diese Vorlage dient nur für [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] und höher, Windows 95 und höher, oder wenn der Stil OFN_EXPLORER vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Das System wird nur einer der angegebenen Vorlagen verwenden. Das System bestimmt die zu verwendende Vorlage basierend auf dem Vorhandensein der OFN_EXPLORER-Stil und das Betriebssystem, das die Anwendung ausgeführt wird. Durch Angabe einer nicht-Explorer und die Explorer-Style-Vorlage, ist es einfach zur Unterstützung von Windows NT 3.51, [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] und höher, Windows 95 und höher.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]Stil Dateidialogfelder unterstützen diese Funktion nicht. Bei dem Versuch, diese Funktion zu verwenden, auf eine [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] Stil Dateidialogfeld löst [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md). Alternativ kann ein benutzerdefiniertes Dialogfeld zu verwenden. Weitere Informationen zur Verwendung einer benutzerdefiniertes `CFileDialog`, finden Sie unter [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912).  
  
##  <a name="startvisualgroup"></a>CFileDialog::StartVisualGroup  
 Deklariert eine optische Gruppe im Dialogfeld. Nachfolgende Aufrufe an jede Methode "add" Hinzufügen dieser Elemente zu dieser Gruppe.  
  
```  
HRESULT StartVisualGroup(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Parameter  
 `dwIDCtl`  
 Die ID der Gruppe "visual".  
  
 `strLabel`  
 Name der Gruppe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="updateofnfromshelldialog"></a>CFileDialog::UpdateOFNFromShellDialog  
 Updates der `m_ofn` Datenstruktur der [CFileDialog](../../mfc/reference/cfiledialog-class.md) basierend auf den aktuellen Zustand des internen Objekts.  
  
```  
void UpdateOFNFromShellDialog();
```  
  
### <a name="remarks"></a>Hinweise  
 In Versionen von Windows vor [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], das Mitglied [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx) -Datenstruktur wurde mit dem Status der fortlaufend synchronisiert die `CFileDialog`. Alle Änderungen an der [M_ofn](#m_ofn) Membervariable den Zustand des Dialogfelds direkt betroffen. Sofort aktualisiert alle Änderungen an den Status im Dialogfeld auch die M_ofn-Membervariable.  
  
 In [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]der `m_ofn` -Datenstruktur wird nicht automatisch aktualisiert. Gewährleisten Sie die Richtigkeit der Daten in der `m_ofn` Membervariable, rufen Sie die `UpdateOFNFromShellDialog` Funktion vor dem Zugriff auf die Daten. Windows ruft diese Funktion während der Verarbeitung der [IFileDialog::OnFileOK](http://msdn.microsoft.com/library/windows/desktop/bb775879).  
  
 Weitere Informationen zur Verwendung der `CFileDialog` Klasse unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel aktualisiert die `CFileDialog` vor der Anzeige. Vor der Aktualisierung der `m_ofn` Membervariable, müssen wir es mit dem aktuellen Status des Dialogfelds zu synchronisieren.  
  
 [!code-cpp[NVC_MFC_CFileDialog&#1;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


