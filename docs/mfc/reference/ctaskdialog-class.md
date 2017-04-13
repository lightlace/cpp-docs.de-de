---
title: CTaskDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
dev_langs:
- C++
helpviewer_keywords:
- CTaskDialog class
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
caps.latest.revision: 29
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
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: d7e0335cc88fbba1a07d86b5e44e040eaad47f2f
ms.lasthandoff: 04/12/2017

---
# <a name="ctaskdialog-class"></a>CTaskDialog Class
Ein Popupdialogfeld, das wie ein Meldungsfeld funktioniert, aber zusätzliche Informationen für den Benutzer anzeigen kann. `CTaskDialog` enthält auch Funktionen zum Erfassen von Informationen des Benutzers.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTaskDialog : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](#ctaskdialog)|Erstellt ein `CTaskDialog`-Objekt.|  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|Fügt eine Befehlsschaltfläche, die `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|Fügt ein Optionsfeld, um die `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Einen Befehl Button-Steuerelement oder eine allgemeine Schaltfläche klickt programmgesteuert.|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Ein Optionsfeld klickt programmgesteuert.|  
|[CTaskDialog::DoModal](#domodal)|Zeigt das `CTaskDialog` an.|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Ruft die Anzahl der verfügbaren allgemeine Schaltflächen ab.|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Konvertiert einen Standard, Windows-Taste, um den allgemeinen Schaltflächentyp zugeordneten, der `CTaskDialog` Klasse.|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|Konvertiert eine allgemeine Schaltflächentypen mit den `CTaskDialog` Klasse, um eine standardmäßige Windows-Schaltfläche.|  
|[CTaskDialog::GetOptions](#getoptions)|Gibt den Optionsflags für diesen `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Gibt den ausgewählten Befehl Button-Steuerelement zurück.|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Gibt den aktivierten Optionsfelds zurück.|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Ruft den Zustand des Kontrollkästchens Überprüfung ab.|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Bestimmt, ob ein Befehl Button-Steuerelement oder eine allgemeine Schaltfläche aktiviert ist.|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Bestimmt, ob ein Optionsfeld aktiviert ist.|  
|[CTaskDialog::IsSupported](#issupported)|Bestimmt, ob der Computer, der die Anwendung ausgeführt wird, unterstützt die `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Fügt den Befehl Schaltflächen-Steuerelemente mit Daten aus der Zeichenfolgentabelle hinzu.|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|Optionsfelder hinzugefügt mithilfe von Daten aus der Tabelle.|  
|[CTaskDialog::NavigateTo](#navigateto)|Überträgt den Fokus auf ein anderes `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Das Framework ruft diese Methode aus, klickt der Benutzer einen Befehl Button-Steuerelement.|  
|[CTaskDialog::OnCreate](#oncreate)|Das Framework ruft diese Methode aus, nach dem Erstellen der `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](#ondestroy)|Das Framework ruft diese Methode auf, unmittelbar bevor sie zerstört die `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Das Framework ruft diese Methode aus, klickt der Benutzer auf die Schaltfläche "Erweitert".|  
|[CTaskDialog::OnHelp](#onhelp)|Das Framework ruft diese Methode auf, wenn der Benutzer die Hilfe anfordert.|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Das Framework ruft diese Methode auf, wenn der Benutzer auf einen Link klickt.|  
|[CTaskDialog::OnInit](#oninit)|Das Framework ruft diese Methode bei der `CTaskDialog` initialisiert wird.|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Das Framework ruft diese Methode aus, wenn der Benutzer den Fokus im Hinblick auf die Steuerelemente verschoben, auf die `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Das Framework ruft diese Methode auf, wenn der Benutzer wählt ein Optionsfeld-Steuerelement aus.|  
|[CTaskDialog::OnTimer](#ontimer)|Das Framework ruft diese Methode beim Ablaufen des Zeitgebers.|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Das Framework ruft diese Methode aus, klickt der Benutzer das Kontrollkästchen für die Überprüfung.|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Entfernt alle Befehl Steuerelemente aus der `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Entfernt die Optionsfelder aus der `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Aktualisiert eine Befehlsschaltfläche auf der `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|Aktualisiert eine Teilmenge der gemeinsamen Schaltflächen UAC erhöhte Rechte benötigt und aktiviert werden.|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Allgemeine Schaltflächen fügt die `CTaskDialog`.|  
|[CTaskDialog::SetContent](#setcontent)|Aktualisiert den Inhalt der `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Gibt das Schaltflächen-Steuerelement von Standard-Befehl.|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Gibt die Standard-Optionsfeld an.|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Passt die Breite der `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Aktualisiert den Clientbereich Erweiterung der `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|Aktualisiert das Symbol "Fußzeile" für die `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](#setfootertext)|Aktualisiert den Text für die Fußzeile der `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](#setmainicon)|Aktualisiert das Symbol "main", der die `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Die wichtigsten Anweisung aktualisiert die `CTaskDialog`.|  
|[CTaskDialog::SetOptions](#setoptions)|Konfiguriert die Optionen für die `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Konfiguriert einen Balken Auswahlrechteck für den `CTaskDialog` und des Dialogfelds "" hinzugefügt.|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|Passt die Position der Statusanzeige an.|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|Passt den Bereich der Statusanzeige an.|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|Legt den Zustand der Statusanzeige fest und zeigt diesen auf die `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Aktiviert oder deaktiviert ein Optionsfeld.|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Legt den Aktivierungszustand des Kontrollkästchens Überprüfung fest.|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Legt den Text auf der rechten Seite des Kontrollkästchens Überprüfung fest.|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Definiert den Titel des der `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](#showdialog)|Erstellt und zeigt eine `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Das Framework ruft diese als Antwort auf verschiedenen Windows-Meldungen.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|`m_aButtons`|Das Array von Befehl Schaltflächen-Steuerelemente für die `CTaskDialog`.|  
|`m_aRadioButtons`|Das Array von Optionsfeld-Steuerelementen für die `CTaskDialog`.|  
|`m_bVerified`|`TRUE`Gibt an, dass das Kontrollkästchen für die Überprüfung aktiviert ist. `FALSE` gibt an, dass es nicht.|  
|`m_footerIcon`|Das Symbol in der Fußzeile der `CTaskDialog`.|  
|`m_hWnd`|Ein Handle für das Fenster für die `CTaskDialog`.|  
|`m_mainIcon`|Das Symbol "main", der die `CTaskDialog`.|  
|`m_nButtonDisabled`|Eine Maske, die welche die allgemeine Schaltflächen angibt, sind deaktiviert.|  
|`m_nButtonElevation`|Eine Maske, die welche die allgemeine Schaltflächen angibt, werden UAC erhöhte Rechte benötigt.|  
|`m_nButtonId`|Die ID des ausgewählten Befehls Button-Steuerelement.|  
|`m_nCommonButton`|Eine Maske, die gibt an, welche allgemeinen Schaltflächen werden angezeigt, auf die `CTaskDialog`.|  
|`m_nDefaultCommandControl`|Die ID der Schaltfläche zu steuern, die ausgewählt wird, wenn die `CTaskDialog` wird angezeigt.|  
|`m_nDefaultRadioButton`|Die ID des Optionsfelds zu steuern, die ausgewählt wird, wenn die `CTaskDialog` wird angezeigt.|  
|`m_nFlags`|Eine Maske, die die Optionen für die `CTaskDialog`.|  
|`m_nProgressPos`|Die aktuelle Position für die Statusanzeige.  Dabei muss es sich um einen Wert zwischen `m_nProgressRangeMin` und `m_nProgressRangeMax` handeln.|  
|`m_nProgressRangeMax`|Der maximale Wert für die Statusanzeige.|  
|`m_nProgressRangeMin`|Der Mindestwert für die Statusanzeige.|  
|`m_nProgressState`|Der Status der Statusanzeige. Weitere Informationen finden Sie unter [CTaskDialog::SetProgressBarState](#setprogressbarstate).|  
|`m_nRadioId`|Die ID des dem ausgewählten Optionsfeld-Steuerelement.|  
|`m_nWidth`|Die Breite der `CTaskDialog` in Pixel.|  
|`m_strCollapse`|Die Zeichenfolge der `CTaskDialog` rechts neben dem Feld Erweiterung zeigt an, wenn die erweiterte Informationen verborgen sind.|  
|`m_strContent`|Die Inhaltszeichenfolge von der `CTaskDialog`.|  
|`m_strExpand`|Die Zeichenfolge der `CTaskDialog` rechts neben dem Feld Erweiterung zeigt an, wenn die erweiterte Informationen angezeigt werden.|  
|`m_strFooter`|Die Fußzeile der `CTaskDialog`.|  
|`m_strInformation`|Die erweiterten Informationen für die `CTaskDialog`.|  
|`m_strMainInstruction`|Die Anweisung von der `CTaskDialog`.|  
|`m_strTitle`|Der Titel des der `CTaskDialog`.|  
|`m_strVerification`|Die Zeichenfolge, die die `CTaskDialog` rechts neben das Kontrollkästchen "Überprüfung" wird angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CTaskDialog` Klasse ersetzt die standardmäßige Windows-Meldungsfeld und verfügt über zusätzliche Funktionen wie neue Steuerelemente zum Sammeln von Informationen vom Benutzer. Diese Klasse ist in der MFC-Bibliothek in [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]. Die `CTaskDialog` steht ab [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Frühere Versionen von Windows können nicht angezeigt werden die `CTaskDialog` Objekt. Verwendung `CTaskDialog::IsSupported` zur Laufzeit bestimmt, ob der aktuelle Benutzer das Aufgabendialogfeld angezeigt werden kann. Das standardmäßige Windows-Meldungsfeld wird weiterhin unterstützt, [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  
  
 Die `CTaskDialog` ist nur beim Erstellen der Anwendung mithilfe der Unicode-Bibliothek verfügbar.  
  
 Die `CTaskDialog` verfügt über zwei verschiedene Konstruktoren. Einen Konstruktor ermöglicht Ihnen die Angabe von zwei Befehlsschaltflächen und maximal sechs regulären Schaltflächen-Steuerelemente. Sie können weitere Befehlsschaltflächen hinzufügen, nach der Erstellung der `CTaskDialog`. Der zweite Konstruktor unterstützt keine Befehlsschaltflächen, aber Sie können eine unbegrenzte Anzahl von regulären Schaltflächen-Steuerelemente hinzufügen. Weitere Informationen zu Konstruktoren, finden Sie unter [CTaskDialog::CTaskDialog](#ctaskdialog).  
  
 Die folgende Abbildung zeigt ein Beispiel für `CTaskDialog` um den Speicherort der einige Steuerelemente zu veranschaulichen.  
  
 ![Beispiel für CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
Beispiel für CTaskDialog  
  
## <a name="requirements"></a>Anforderungen  
 **Minimal erforderliches Betriebssystem:**[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
 **Header:** afxtaskdialog.h  
  
##  <a name="addcommandcontrol"></a>CTaskDialog::AddCommandControl  
 Fügt ein neuen Befehl Schaltflächen-Steuerelement an die `CTaskDialog`.  
  
```  
void AddCommandControl(
    int nCommandControlID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Der Befehl Steuerelement-ID.  
  
 [in] `strCaption`  
 Die Zeichenfolge, die die `CTaskDialog` zeigt dem Benutzer an. Verwenden Sie diese Zeichenfolge, um den Zweck des Befehls zu erläutern.  
  
 [in] `bEnabled`  
 Ein boolescher Parameter, der angibt, ob die Schaltfläche "Neu" aktiviert oder deaktiviert ist.  
  
 [in] `bRequiresElevation`  
 Ein boolescher Parameter, der angibt, ob ein Befehl Erhöhung der Rechte erfordert.  
  
### <a name="remarks"></a>Hinweise  
 Die `CTaskDialog Class` kann eine unbegrenzte Anzahl von Schaltflächen-Steuerelemente Befehl anzeigen. Jedoch, wenn eine `CTaskDialog` zeigt alle Befehlsschaltfläche gesteuert, es können maximal sechs Schaltflächen angezeigt. Wenn eine `CTaskDialog` wurde kein Befehl Schaltflächen-Steuerelemente, es kann eine unbegrenzte Anzahl von Schaltflächen angezeigt.  
  
 Wenn der Benutzer wählt ein Befehl Schaltflächen-Steuerelement aus der `CTaskDialog` geschlossen wird. Wenn Ihre Anwendung mithilfe des Dialogfelds "" zeigt [CTaskDialog::DoModal](#domodal), `DoModal` gibt die `nCommandControlID` des ausgewählten Befehls Schaltflächen-Steuerelements.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="addradiobutton"></a>CTaskDialog::AddRadioButton  
 Fügt ein Optionsfeld, um die `CTaskDialog`.  
  
```  
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID des Optionsfelds.  
  
 [in] `strCaption`  
 Die Zeichenfolge, die die `CTaskDialog` neben der Schaltfläche "Radio" angezeigt.  
  
 [in] `bEnabled`  
 Ein boolescher Parameter, der angibt, ob das Optionsfeld aktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Optionsfelder für die [CTaskDialog Klasse](../../mfc/reference/ctaskdialog-class.md) ermöglichen es Ihnen, Informationen vom Benutzer zu erfassen. Verwenden Sie die Funktion [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) zu bestimmen, welches Optionsfeld aktiviert ist.  
  
 Die `CTaskDialog` nicht erfordert, dass die `nRadioButtonID` Parameter für jedes Optionsfeld eindeutig sind. Allerdings können Sie unerwartetes Verhalten kommen, wenn Sie keinen unterschiedliche Bezeichner für jedes Optionsfeld verwenden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="clickcommandcontrol"></a>CTaskDialog::ClickCommandControl  
 Einen Befehl Button-Steuerelement oder eine allgemeine Schaltfläche klickt programmgesteuert.  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die Befehls-ID des Steuerelements klicken.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode generiert, die Windows-Meldung `TDM_CLICK_BUTTON`.  
  
##  <a name="clickradiobutton"></a>CTaskDialog::ClickRadioButton  
 Ein Optionsfeld klickt programmgesteuert.  
  
```  
protected:  
void ClickRadioButton(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID des Optionsfelds auf.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode generiert, die Windows-Meldung `TDM_CLICK_RADIO_BUTTON`.  
  
##  <a name="ctaskdialog"></a>CTaskDialog::CTaskDialog  
 Erstellt eine Instanz der [CTaskDialog Klasse](../../mfc/reference/ctaskdialog-class.md).  
  
```  
CTaskDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));

 
CTaskDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast,  
    int nCommonButtons,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strContent`  
 Die Zeichenfolge, die für den Inhalt des verwenden die `CTaskDialog`.  
  
 [in] `strMainInstruction`  
 Die Anweisung von der `CTaskDialog`.  
  
 [in] `strTitle`  
 Der Titel des der `CTaskDialog`.  
  
 [in] `nCommonButtons`  
 Eine Maske der allgemeinen Schaltflächen Hinzufügen der `CTaskDialog`.  
  
 [in] `nTaskDialogOptions`  
 Der Satz von Optionen für die `CTaskDialog`.  
  
 [in] `strFooter`  
 Das als Fußzeile zu verwendende Zeichenfolge.  
  
 [in] `nIDCommandControlsFirst`  
 Die Zeichenfolgen-ID des ersten Befehls.  
  
 [in] `nIDCommandControlsLast`  
 Die Zeichenfolgen-ID des letzten Befehls.  
  
### <a name="remarks"></a>Hinweise  
 Es gibt zwei Möglichkeiten, die Sie hinzufügen, können eine `CTaskDialog` für Ihre Anwendung. Die erste Möglichkeit ist die Verwendung eines Konstruktors zum Erstellen einer `CTaskDialog` und zeigen Sie es mit [CTaskDialog::DoModal](#domodal). Die zweite Möglichkeit ist die Verwendung die statische Funktion [CTaskDialog::ShowDialog](#showdialog), können Sie zum Anzeigen einer `CTaskDialog` ohne explizites erstellen eine `CTaskDialog` Objekt.  
  
 Der zweite Konstruktor erstellt Befehl Schaltflächen-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Zeichenfolgentabelle in der Ressourcendatei hat mehrere Zeichenfolgen mit zugeordneten IDs. Diese Methode fügt einen Befehl Button-Steuerelement für jeden gültigen Eintrag in der Zeichenfolgentabelle zwischen `nIDCommandControlsFirst` und `nCommandControlsLast`(einschließlich). Für diesen Befehl Schaltflächen-Steuerelemente, die Zeichenfolge in der Zeichenfolgentabelle ist die Beschriftung des Steuerelements, und die Zeichenfolgen-ID ist das Steuerelement-ID.  
  
 Finden Sie unter [CTaskDialog::SetOptions](#setoptions) eine Liste der gültigen Optionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="domodal"></a>CTaskDialog::DoModal  
 Zeigt die `CTaskDialog` ab und wandelt diesen gebunden.  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hParent`  
 Das übergeordnete Fenster für die `CTaskDialog`.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die vom Benutzer vorgenommene Auswahl entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Zeigt diese Instanz die [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Klicken Sie dann die Anwendung wartet, bis der Benutzer das Dialogfeld zu schließen.  
  
 Die `CTaskDialog` wird geschlossen, wenn der Benutzer eine allgemeine-Schaltfläche, ein Link-Steuerelement wählt, oder schließt die `CTaskDialog`. Der Rückgabewert ist der Bezeichner, der angibt, wie der Benutzer das Dialogfeld geschlossen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getcommonbuttoncount"></a>CTaskDialog::GetCommonButtonCount  
 Ruft die Anzahl der allgemeinen Schaltflächen ab.  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der allgemeinen Schaltflächen zur Verfügung.  
  
### <a name="remarks"></a>Hinweise  
 Die allgemeine Schaltflächen sind die Standardschaltflächen, die Sie bereitstellen [CTaskDialog::CTaskDialog](#ctaskdialog). Die [CTaskDialog Klasse](../../mfc/reference/ctaskdialog-class.md) Schaltflächen am unteren Rand des Dialogfelds angezeigt.  
  
 Die Aufzählungsliste der Schaltflächen wird in CommCtrl.h bereitgestellt.  
  
##  <a name="getcommonbuttonflag"></a>CTaskDialog::GetCommonButtonFlag  
 Konvertiert einen Standard, Windows-Taste, um den allgemeinen Schaltflächentyp zugeordneten, der [CTaskDialog Klasse](../../mfc/reference/ctaskdialog-class.md).  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nButtonId`  
 Der standardmäßige Wert der Windows-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des entsprechenden `CTaskDialog` allgemeine Schaltfläche. Wenn keine entsprechenden allgemeine Schaltfläche vorhanden ist, gibt diese Methode 0 zurück.  
  
##  <a name="getcommonbuttonid"></a>CTaskDialog::GetCommonButtonId  
 Konvertiert eine allgemeine Schaltflächentypen mit den [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) mit einer standardmäßigen Windows-Schaltfläche.  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlag`  
 Allgemeine Schaltflächentyp zugeordneten der `CTaskDialog` Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der die entsprechenden standard-Windows-Taste. Es ist keine entsprechende Windows-Taste, gibt die Methode 0 zurück.  
  
##  <a name="getoptions"></a>CTaskDialog::GetOptions  
 Gibt den Optionsflags für diesen `CTaskDialog`.  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Flags für die `CTaskDialog`.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den Optionen zur Verfügung, um die [CTaskDialog Klasse](../../mfc/reference/ctaskdialog-class.md), finden Sie unter [CTaskDialog::SetOptions](#setoptions).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getselectedcommandcontrolid"></a>CTaskDialog::GetSelectedCommandControlID  
 Gibt den ausgewählten Befehl Button-Steuerelement zurück.  
  
```  
int GetSelectedCommandControlID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ID der aktuell ausgewählten Befehl Button-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen keinen verwenden Sie diese Methode zum Abrufen der ID für die Befehlsschaltfläche, die der Benutzer ausgewählt. Diese ID wird zurückgegeben, entweder durch [CTaskDialog::DoModal](#domodal) oder [CTaskDialog::ShowDialog](#showdialog).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="getselectedradiobuttonid"></a>CTaskDialog::GetSelectedRadioButtonID  
 Gibt den aktivierten Optionsfelds zurück.  
  
```  
int GetSelectedRadioButtonID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ID des ausgewählten Optionsfelds.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode verwenden, nachdem der Benutzer das Dialogfeld zum Abrufen des aktivierten Optionsfelds wird geschlossen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="getverificationcheckboxstate"></a>CTaskDialog::GetVerificationCheckboxState  
 Ruft den Zustand des Kontrollkästchens Überprüfung ab.  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie dieses Kontrollkästchen aktiviert ist, `FALSE` wird jedoch nicht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="iscommandcontrolenabled"></a>CTaskDialog::IsCommandControlEnabled  
 Bestimmt, ob ein Befehl Button-Steuerelement oder eine Schaltfläche aktiviert ist.  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die ID des Befehls Button-Steuerelement oder eine Schaltfläche zu testen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Steuerelement aktiviert ist, `FALSE` wird jedoch nicht.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode verwenden, um zu bestimmen, die Verfügbarkeit von sowohl Befehl Schaltflächen-Steuerelemente und die allgemeine Schaltflächen von der `CTaskDialog Class`.  
  
 Wenn `nCommandControlID` ist kein gültiger Bezeichner für entweder eine häufige `CTaskDialog` Schaltfläche oder ein Befehl Schaltflächen-, löst diese Methode eine Ausnahme aus.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="isradiobuttonenabled"></a>CTaskDialog::IsRadioButtonEnabled  
 Bestimmt, ob ein Optionsfeld aktiviert ist.  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID des Optionsfelds zu testen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie das Optionsfeld aktiviert ist, `FALSE` wird jedoch nicht.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nRadioButtonID` ist kein gültiger Bezeichner für ein Optionsfeld, diese Methode löst eine Ausnahme aus.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="issupported"></a>CTaskDialog::IsSupported  
 Bestimmt, ob der Computer, der die Anwendung ausgeführt wird, unterstützt die `CTaskDialog`.  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Computer unterstützt das `CTaskDialog`; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können zur Laufzeit bestimmen Sie, ob der Computer, die Ihre Anwendung ausgeführt wird, unterstützt die `CTaskDialog Class`. Wenn der Computer nicht unterstützt die `CTaskDialog`, sollten Sie eine andere Methode zum Kommunizieren von Informationen an den Benutzer bereitstellen. Die Anwendung abstürzt, wenn versucht wird, verwenden Sie eine `CTaskDialog` auf einem Computer, die nicht unterstützt wird die `CTaskDialog` Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="loadcommandcontrols"></a>CTaskDialog::LoadCommandControls  
 Fügt den Befehl Schaltflächen-Steuerelemente mit Daten aus der Zeichenfolgentabelle hinzu.  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIDCommandControlsFirst`  
 Die Zeichenfolgen-ID des ersten Befehls.  
  
 [in] `nIDCommandControlsLast`  
 Die Zeichenfolgen-ID des letzten Befehls.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt Befehl Schaltflächen-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Zeichenfolgentabelle in der Ressourcendatei hat mehrere Zeichenfolgen mit zugeordneten IDs. Neuen Befehl Schaltflächensteuerelemente hinzugefügt, die mit dieser Methode verwenden Sie die Zeichenfolge für die Beschriftung des Steuerelements und der Zeichenfolgen-ID für das Steuerelement-ID. Der Bereich der ausgewählten Zeichenfolgen gebotenen `nIDCommandControlsFirst` und `nCommandControlsLast`(einschließlich). Wenn im Bereich ein leerer Eintrag vorhanden ist, ist die Methode kein Befehl Schaltflächen-Steuerelement für diesen Eintrag hinzufügen.  
  
 Standardmäßig werden neue Befehl Schaltflächensteuerelemente aktiviert sind und erfordern keine Erhöhung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="loadradiobuttons"></a>CTaskDialog::LoadRadioButtons  
 RadioButton-Steuerelementen hinzugefügt mithilfe von Daten aus der Tabelle.  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIDRadioButtonsFirst`  
 Die Zeichenfolgen-ID, der das erste Optionsfeld.  
  
 [in] `nIDRadioButtonsLast`  
 Die Zeichenfolgen-ID des letzten Optionsfelds.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt Optionsfelder mit Daten aus der Ressourcendatei der Anwendung. Die Zeichenfolgentabelle in der Ressourcendatei hat mehrere Zeichenfolgen mit zugeordneten IDs. Neue Optionsfelder, die mit dieser Methode hinzugefügt und verwenden Sie die Zeichenfolge für das Optionsfeld Beschriftung und die Zeichenfolgen-ID für das Optionsfeld-ID. Der Bereich der ausgewählten Zeichenfolgen gebotenen `nIDRadioButtonsFirst` und `nRadioButtonsLast`(einschließlich). Wenn im Bereich ein leerer Eintrag vorhanden ist, ist die Methode ein Optionsfeld für diesen Eintrag nicht hinzufügen.  
  
 Standardmäßig sind neue Optionsfelder aktiviert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="navigateto"></a>CTaskDialog::NavigateTo  
 Überträgt den Fokus auf ein anderes `CTaskDialog`.  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `oTaskDialog`  
 Die `CTaskDialog` , die den Fokus erhält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode blendet Sie aus der aktuellen `CTaskDialog` Anzeige der `oTaskDialog`. Die `oTaskDialog` angezeigt wird, am gleichen Speicherort wie die aktuelle `CTaskDialog`.  
  
##  <a name="oncommandcontrolclick"></a>CTaskDialog::OnCommandControlClick  
 Das Framework ruft diese Methode aus, klickt der Benutzer einen Befehl Button-Steuerelement.  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die ID der Befehlsschaltfläche, die der Benutzer ausgewählt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="oncreate"></a>CTaskDialog::OnCreate  
 Das Framework ruft diese Methode aus, nach dem Erstellen der `CTaskDialog`.  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="ondestroy"></a>CTaskDialog::OnDestroy  
 Das Framework ruft diese Methode auf, unmittelbar bevor sie zerstört die `CTaskDialog`.  
  
```  
virtual HRESULT OnDestroy();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="onexpandbuttonclick"></a>CTaskDialog::OnExpandButtonClick  
 Das Framework ruft diese Methode aus, klickt der Benutzer auf die Schaltfläche "Erweitert".  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bExpanded`  
 Ein Wert ungleich Null gibt an, dass die zusätzliche Informationen angezeigt werden. 0 gibt an, dass die zusätzliche Informationen verborgen sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="onhelp"></a>CTaskDialog::OnHelp  
 Das Framework ruft diese Methode auf, wenn der Benutzer die Hilfe anfordert.  
  
```  
virtual HRESULT OnHelp();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="onhyperlinkclick"></a>CTaskDialog::OnHyperlinkClick  
 Das Framework ruft diese Methode auf, wenn der Benutzer auf einen Link klickt.  
  
```  
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strHref`  
 Die Zeichenfolge, die den Link darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) vor dem Zurückgeben `S_OK`.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="oninit"></a>CTaskDialog::OnInit  
 Das Framework ruft diese Methode bei der `CTaskDialog` initialisiert wird.  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="onnavigatepage"></a>CTaskDialog::OnNavigatePage  
 Das Framework ruft diese Methode als Antwort auf die [CTaskDialog::NavigateTo](#navigateto) Methode.  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="onradiobuttonclick"></a>CTaskDialog::OnRadioButtonClick  
 Das Framework ruft diese Methode auf, wenn der Benutzer wählt ein Optionsfeld-Steuerelement aus.  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID der das Optionsfeld-Steuerelement, das der Benutzer geklickt hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="ontimer"></a>CTaskDialog::OnTimer  
 Das Framework ruft diese Methode beim Ablaufen des Zeitgebers.  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lTime`  
 Zeit in Millisekunden seit dem `CTaskDialog` erstellt wurde oder der Timer zurückgesetzt wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="onverificationcheckboxclick"></a>CTaskDialog::OnVerificationCheckboxClick  
 Das Framework ruft diese Methode aus, klickt der Benutzer das Kontrollkästchen für die Überprüfung.  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bChecked`  
 `TRUE`Gibt an, dass das Kontrollkästchen für die Überprüfung aktiviert ist. `FALSE` gibt an, dass es nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Verhaltens.  
  
##  <a name="removeallcommandcontrols"></a>CTaskDialog::RemoveAllCommandControls  
 Entfernt alle Befehl Schaltflächensteuerelemente aus der `CTaskDialog`.  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="removeallradiobuttons"></a>CTaskDialog::RemoveAllRadioButtons  
 Entfernt die Optionsfelder aus der `CTaskDialog`.  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setcommandcontroloptions"></a>CTaskDialog::SetCommandControlOptions  
 Aktualisiert eine Befehlsschaltfläche auf der `CTaskDialog`.  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die ID des Steuerelements zu aktualisieren.  
  
 [in] `bEnabled`  
 Ein boolescher Parameter, der angibt, ob der angegebene Befehl Button-Steuerelement aktiviert oder deaktiviert ist.  
  
 [in] `bRequiresElevation`  
 Ein boolescher Parameter, der angibt, ob der angegebene Befehl Button-Steuerelement Erhöhung der Rechte ist erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie ändern, ob ein Befehl Schaltflächen-Steuerelement aktiviert ist, oder erfordert erhöhte Rechte, nachdem er hinzugefügt wurde die `CTaskDialog Class`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setcommonbuttonoptions"></a>CTaskDialog::SetCommonButtonOptions  
 Aktualisiert eine Teilmenge der allgemeine Schaltflächen, die zu aktivierenden und UAC-heraufstufung erforderlich ist.  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nDisabledButtonMask`  
 Eine Maske für die allgemeine Schaltflächen zu deaktivieren.  
  
 [in] `nElevationButtonMask`  
 Eine Maske für die allgemeine Schaltflächen, die Erhöhung der Rechte erfordern.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die allgemeine Schaltflächen zur Verfügung festlegen, mit einer Instanz von der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) wird mit dem Konstruktor [CTaskDialog::CTaskDialog](#ctaskdialog) und die Methode [CTaskDialog::SetCommonButtons](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions`Hinzufügen von neuen allgemeinen Schaltflächen unterstützt nicht.  
  
 Wenn Sie mit dieser Methode können deaktivieren, oder erhöhen eine allgemeine Schaltfläche, die für diese nicht verfügbar ist `CTaskDialog`, diese Methode löst eine Ausnahme aus, mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro.  
  
 Mit dieser Methode können keine der Schaltflächen, die zur Verfügung steht die `CTaskDialog` jedoch befindet sich nicht in der `nDisabledButtonMask`, selbst wenn diese zuvor deaktiviert war. Diese Methode Erhöhung der Rechte auf ähnliche Weise behandelt: er zeichnet allgemeine Schaltflächen keine Erhöhung der Rechte erfordern, ist die Schaltfläche "common" verfügbar, aber nicht im enthalten `nElevationButtonMask`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog 6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcommonbuttons"></a>CTaskDialog::SetCommonButtons  
 Allgemeine Schaltflächen fügt die `CTaskDialog`.  
  
```  
void SetCommonButtons(
    int nButtonMask,  
    int nDisabledButtonMask = 0,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nButtonMask`  
 Eine Maske der Schaltflächen zum Hinzufügen der `CTaskDialog`.  
  
 [in] `nDisabledButtonMask`  
 Eine Maske der Schaltflächen zu deaktivieren.  
  
 [in] `nElevationButtonMask`  
 Eine Maske für die Schaltflächen, die Erhöhung der Rechte erfordern.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode nach der Anzeige des Ablaufverfolgungsfensters für diese Instanz Aufrufen der `CTaskDialog Class` wird erstellt. Wenn Sie dies tun, löst diese Methode eine Ausnahme aus.  
  
 Die Schaltflächen erkennbar `nButtonMask` überschreiben alle gemeinsamen Schaltflächen, die zuvor hinzugefügt wurde die `CTaskDialog`. Nur die Schaltflächen im angegebenen `nButtonMask` verfügbar sind.  
  
 Wenn entweder `nDisabledButtonMask` oder `nElevationButtonMask` enthalten eine Schaltfläche, der nicht `nButtonMask`, diese Methode löst eine Ausnahme aus, mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro.  
  
 Standardmäßig werden alle allgemeinen Schaltflächen aktiviert sind und erfordern keine Erhöhung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog 6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcontent"></a>CTaskDialog::SetContent  
 Aktualisiert den Inhalt der `CTaskDialog`.  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strContent`  
 Die Zeichenfolge, die dem Benutzer angezeigt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Inhalt der `CTaskDialog Class` ist der Text, der dem Benutzer im Abschnitt "main" im Dialogfeld angezeigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setdefaultcommandcontrol"></a>CTaskDialog::SetDefaultCommandControl  
 Gibt das Schaltflächen-Steuerelement von Standard-Befehl.  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die ID des Schaltflächensteuerelements Befehl als Standard.  
  
### <a name="remarks"></a>Hinweise  
 Das Schaltflächen-Steuerelement von Standard-Befehl wird das Steuerelement, das ausgewählt, wenn die `CTaskDialog` zuerst an den Benutzer angezeigt wird.  
  
 Diese Methode löst eine Ausnahme aus, die Befehlsschaltfläche gemäß gefunden `nCommandControlID`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setdefaultradiobutton"></a>CTaskDialog::SetDefaultRadioButton  
 Gibt die Standard-Optionsfeld an.  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID des Optionsfelds ist die Standardeinstellung.  
  
### <a name="remarks"></a>Hinweise  
 Das Optionsfeld standardmäßig ist die Schaltfläche ausgewählt, wenn die `CTaskDialog` zuerst an den Benutzer angezeigt wird.  
  
 Diese Methode löst eine Ausnahme aus, wenn er das Optionsfeld gemäß finden kann `nRadioButtonID`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setdialogwidth"></a>CTaskDialog::SetDialogWidth  
 Passt die Breite der `CTaskDialog`.  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nWidth`  
 Die Breite des Dialogfelds in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `nWidth` muss größer als oder gleich 0 sein. Andernfalls löst diese Methode eine Ausnahme aus.  
  
 Wenn `nWidth` ist auf 0 festgelegt, legt diese Methode, die das Dialogfeld, um die Standardgröße.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setexpansionarea"></a>CTaskDialog::SetExpansionArea  
 Aktualisiert den Clientbereich Erweiterung der `CTaskDialog`.  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strExpandedInformation`  
 Die Zeichenfolge, die die `CTaskDialog` im Hauptteil des Dialogfelds zeigt an, wenn der Benutzer die Schaltfläche "Erweitert" klickt.  
  
 [in] `strCollapsedLabel`  
 Die Zeichenfolge, die die `CTaskDialog` neben der Schaltfläche "Erweitert" zeigt an, wenn der erweiterte Bereich reduziert wird.  
  
 [in] `strExpandedLabel`  
 Die Zeichenfolge, die die `CTaskDialog` neben der Schaltfläche "Erweitert" zeigt an, wenn der erweiterte Bereich angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Bereich erweitert, der die `CTaskDialog Class` ermöglicht Ihnen, zusätzliche Informationen für den Benutzer zu senden. Der Bereich für die Erweiterung befindet sich im Hauptteil der der `CTaskDialog`befindet sich direkt unter den Titel und den Inhalt der Zeichenfolge.  
  
 Wenn die `CTaskDialog` steht an erster Stelle angezeigt, es nicht die erweiterte Informationen angezeigt und setzt `strCollapsedLabel` neben der Schaltfläche "Erweitert". Klickt der Benutzer die Schaltfläche "Erweitert" die `CTaskDialog` zeigt `strExpandedInformation` und ändert die Bezeichnung `strExpandedLabel`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootericon"></a>CTaskDialog::SetFooterIcon  
 Aktualisiert das Symbol "Fußzeile", der die `CTaskDialog`.  
  
```  
void SetFooterIcon(HICON hFooterIcon);  
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hFooterIcon`  
 Das Symbol "Neu", für die `CTaskDialog`.  
  
 [in] `lpszFooterIcon`  
 Das Symbol "Neu", für die `CTaskDialog`.  
  
### <a name="remarks"></a>Hinweise  
 Das Symbol "Fußzeile" wird angezeigt, am unteren Rand der [CTaskDialog Klasse](../../mfc/reference/ctaskdialog-class.md). Sie können FooterText zugeordnet. Sie können Text in die Fußzeile mit ändern [CTaskDialog::SetFooterText](#setfootertext).  
  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro Wenn die `CTaskDialog` angezeigt wird oder der Eingabeparameter ist `NULL`.  
  
 Ein `CTaskDialog` lässt nur eine `HICON` oder `LPCWSTR` als Fußzeile-Symbol. Dies wird durch Festlegen der Option konfiguriert `TDF_USE_HICON_FOOTER` im Konstruktor oder [CTaskDialog::SetOptions](#setoptions). Wird standardmäßig die `CTaskDialog` für die Verwendung konfiguriert `LPCWSTR` als Eingabetyp für das Symbol "Fußzeile". Diese Methode generiert eine Ausnahme aus, wenn Sie versuchen, das Symbol mit nicht zulässigen Typ festzulegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootertext"></a>CTaskDialog::SetFooterText  
 Aktualisiert den Text für die Fußzeile der `CTaskDialog`.  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strFooterText`  
 Der neue Text für die Fußzeile.  
  
### <a name="remarks"></a>Hinweise  
 Das Footer-Symbol wird neben den Footertext am unteren Rand der `CTaskDialog`. Sie können ändern, dass das Symbol "Fußzeile" mit [CTaskDialog::SetFooterIcon](#setfootericon).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmainicon"></a>CTaskDialog::SetMainIcon  
 Aktualisiert das Symbol "main", der die `CTaskDialog`.  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMainIcon`  
 Das Symbol "Neu".  
  
 [in] `lpszMainIcon`  
 Das Symbol "Neu".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro Wenn die `CTaskDialog` angezeigt wird oder der Eingabeparameter ist `NULL`.  
  
 Ein `CTaskDialog` lässt nur eine `HICON` oder `LPCWSTR` als Haupt-Symbol. Können Sie konfigurieren, indem die `TDF_USE_HICON_MAIN` Option im Konstruktor oder in der [CTaskDialog::SetOptions](#setoptions) Methode. Wird standardmäßig die `CTaskDialog` für die Verwendung konfiguriert `LPCWSTR` als Eingabetyp für das Symbol "main". Diese Methode generiert eine Ausnahme aus, wenn Sie versuchen, das Symbol mit nicht zulässigen Typ festzulegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmaininstruction"></a>CTaskDialog::SetMainInstruction  
 Die wichtigsten Anweisung aktualisiert die `CTaskDialog`.  
  
```  
void SetMainInstruction(const CString& strInstructions);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strInstructions`  
 Die neue Anweisung.  
  
### <a name="remarks"></a>Hinweise  
 Die Anweisung von der `CTaskDialog Class` Text in großer Schriftart fett an den Benutzer angezeigt wird. Es befindet sich unterhalb der Titelleiste des Dialogfelds "-".  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setoptions"></a>CTaskDialog::SetOptions  
 Konfiguriert die Optionen für die `CTaskDialog`.  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOptionFlag`  
 Die Gruppe von Flags für die Verwendung der `CTaskDialog`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löscht die aktuellen Optionen für die `CTaskDialog`. Um die aktuellen Optionen zu erhalten, Sie müssen rufen sie zuerst mit [CTaskDialog::GetOptions](#getoptions) und kombinieren Sie diese mit den Optionen, die Sie festlegen möchten.  
  
 Die folgende Tabelle enthält die gültigen Optionen.  
  
 `TDF_ENABLE_HYPERLINKS`  
 Ermöglicht die Links in der `CTaskDialog`.  
  
 `TDF_USE_HICON_MAIN`  
 Konfiguriert die `CTaskDialog` verwenden eine `HICON` für das Symbol "main". Die Alternative ist die Verwendung einer `LPCWSTR`.  
  
 `TDF_USE_HICON_FOOTER`  
 Konfiguriert die `CTaskDialog` verwenden eine `HICON` für das Symbol "Fußzeile". Die Alternative ist die Verwendung einer `LPCWSTR`.  
  
 `TDF_ALLOW_DIALOG_CANCELLATION`  
 Ermöglicht es dem Benutzer zu schließen die `CTaskDialog` mithilfe der Tastatur oder mithilfe des Symbols in der Ecke oben rechts im Dialogfeld auch dann, wenn die **"Abbrechen"** Schaltfläche ist nicht aktiviert. Wenn dieses Flag nicht festgelegt ist und die **"Abbrechen"** Schaltfläche ist nicht aktiviert, kann nicht der Benutzer das Dialogfeld schließen, mithilfe von Alt + F4 drücken die ESC-Taste oder der Titelleiste Schließ-Schaltfläche.  
  
 `TDF_USE_COMMAND_LINKS`  
 Konfiguriert die `CTaskDialog` Befehl Schaltflächen-Steuerelemente verwenden.  
  
 `TDF_USE_COMMAND_LINKS_NO_ICON`  
 Konfiguriert die `CTaskDialog` Befehl Schaltflächen-Steuerelemente verwenden, ohne dass ein Symbol neben dem Steuerelement angezeigt. `TDF_USE_COMMAND_LINKS` überschreibt `TDF_USE_COMMAND_LINKS_NO_ICON`.  
  
 `TDF_EXPAND_FOOTER_AREA`  
 Gibt an, dass derzeit der Expansion-Bereich erweitert wird.  
  
 `TDF_EXPANDED_BY_DEFAULT`  
 Bestimmt, ob die Erweiterung Bereich standardmäßig erweitert wird.  
  
 `TDF_VERIFICATION_FLAG_CHECKED`  
 Gibt an, dass das Kontrollkästchen für die Überprüfung derzeit ausgewählt ist.  
  
 `TDF_SHOW_PROGRESS_BAR`  
 Konfiguriert die `CTaskDialog` eine Statusanzeige angezeigt.  
  
 `TDF_SHOW_MARQUEE_PROGRESS_BAR`  
 Konfiguriert die Statusanzeige, um eine Statusanzeige Laufschrift sein. Wenn Sie diese Option aktivieren, müssen Sie festlegen `TDF_SHOW_PROGRESS_BAR` das erwartete Verhalten aufweisen.  
  
 `TDF_CALLBACK_TIMER`  
 Gibt an, dass die `CTaskDialog` Rückruf Intervall auf ca. 200 Millisekunden festgelegt ist.  
  
 `TDF_POSITION_RELATIVE_TO_WINDOW`  
 Konfiguriert die `CTaskDialog` relativ zum übergeordneten Fenster zentriert werden soll. Wenn dieses Flag nicht aktiviert ist, die `CTaskDialog` ist relativ zu dem Monitor zentriert.  
  
 `TDF_RTL_LAYOUT`  
 Konfiguriert die `CTaskDialog` für rechts-nach-links-lesen-Layout.  
  
 `TDF_NO_DEFAULT_RADIO_BUTTON`  
 Gibt an, dass keine Schaltfläche "Radio" ausgewählt ist bei der `CTaskDialog` angezeigt wird.  
  
 `TDF_CAN_BE_MINIMIZED`  
 Ermöglicht es dem Benutzer zur Minimierung der `CTaskDialog`. Diese Option unterstützt die `CTaskDialog` kann nicht gebunden werden. MFC unterstützt diese Option, da MFC eine ohne Modus nicht unterstützt `CTaskDialog`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setprogressbarmarquee"></a>CTaskDialog::SetProgressBarMarquee  
 Konfiguriert einen Balken Auswahlrechteck für den `CTaskDialog` und des Dialogfelds "" hinzugefügt.  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnabled`  
 `TRUE`So aktivieren Sie die Leiste Laufschrift; `FALSE` zum Deaktivieren der Laufschrift-Leiste, und entfernen Sie es aus der `CTaskDialog`.  
  
 [in] `nMarqueeSpeed`  
 Eine ganze Zahl, die die Geschwindigkeit des Laufschrift Balkens angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Laufschrift Befehlsleiste wird angezeigt, darunter den Haupttext der `CTaskDialog Class`.  
  
 Verwendung `nMarqueeSpeed` festzulegende die Geschwindigkeit des Balkens Laufschrift; größere Werte zeigen einen langsamer. Der Wert 0 für `nMarqueeSpeed` macht die Laufschrift Leiste mit der Geschwindigkeit der Standard für verschieben [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro Wenn `nMarqueeSpeed` ist kleiner als 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarposition"></a>CTaskDialog::SetProgressBarPosition  
 Passt die Position der Statusanzeige an.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nProgressPos`  
 Die Position der Statusanzeige auf.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro Wenn `nProgressPos` liegt nicht im Bereich Status-Leiste. Sie können den Fortschritt Leiste Bereich mit ändern [CTaskDialog::SetProgressBarRange](#setprogressbarrange).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarrange"></a>CTaskDialog::SetProgressBarRange  
 Passt den Bereich der Statusanzeige an.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRangeMin`  
 Die untere Grenze der Statusanzeige.  
  
 [in] `nRangeMax`  
 Die obere Grenze der Statusanzeige.  
  
### <a name="remarks"></a>Hinweise  
 Die Position der Statusanzeige ist relativ zum `nRangeMin` und `nRangeMax`. Z. B. wenn `nRangeMin` lautet "50" und `nRangeMax` ist 100, eine Position von 75 genau über die Statusanzeige. Verwendung [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) , die Position der Statusanzeige festzulegen.  
  
 In einer Fortschrittsanzeige Balken-, die Option `TDF_SHOW_PROGRESS_BAR` muss aktiviert sein und `TDF_SHOW_MARQUEE_PROGRESS_BAR` darf nicht aktiviert sein. Diese Methode automatisch legt `TDF_SHOW_PROGRESS_BAR` und löscht `TDF_SHOW_MARQUEE_PROGRESS_BAR`. Verwendung [CTaskDialog::SetOptions](#setoptions) so ändern die Optionen für diese Instanz manuell die [CTaskDialog Klasse](../../mfc/reference/ctaskdialog-class.md).  
  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro Wenn `nRangeMin` ist nicht kleiner als `nRangeMax`. Diese Methode löst auch eine Ausnahme aus, wenn die `CTaskDialog` wird bereits angezeigt und verfügt über eine Laufschrift Statusanzeige angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarstate"></a>CTaskDialog::SetProgressBarState  
 Legt den Zustand der Statusanzeige fest und zeigt diesen auf die `CTaskDialog`.  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nState`  
 Der Status der Statusanzeige. Finden Sie im Abschnitt "Hinweise" die möglichen Werte ein.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro Wenn die `CTaskDialog` wird bereits angezeigt und verfügt über eine Laufschrift Statusanzeige angezeigt.  
  
 Die folgende Tabelle enthält die möglichen Werte für `nState`. In all diesen Fällen werden die Statusanzeige mit der regulären Farbe ausgefüllt, bis sie die Stoppposition des angegebenen erreicht. An diesem Punkt wird anhand des Zustands Farbe geändert.  
  
 PBST_NORMAL  
 Nach dem Fortschritt Leiste füllt die `CTaskDialog` ändert sich nicht auf die Farbe des Balkens. Standardmäßig ist die reguläre Farbe Grün.  
  
 PBST_ERROR  
 Nach dem Fortschritt Leiste füllt die `CTaskDialog` ändert sich die Farbe des Balkens der Farbe Fehler. Standardmäßig ist dies ein Rot.  
  
 PBST_PAUSED  
 Nach dem Fortschritt Leiste füllt die `CTaskDialog` ändert sich die Farbe des Balkens der angehaltenen Farbe. Standardmäßig ist dies gelb.  
  
 Sie können festlegen, in denen die Statusanzeige mit beendet [CTaskDialog::SetProgressBarPosition](#setprogressbarposition).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setradiobuttonoptions"></a>CTaskDialog::SetRadioButtonOptions  
 Aktiviert oder deaktiviert ein Optionsfeld.  
  
```  
void SetRadioButtonOptions(
    int nRadioButtonID,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID der das Optionsfeld-Steuerelement.  
  
 [in] `bEnabled`  
 `TRUE`So aktivieren Sie das Optionsfeld; `FALSE` So deaktivieren Sie das Optionsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro Wenn `nRadioButtonID` ist keine gültige ID für ein Optionsfeld.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setverificationcheckbox"></a>CTaskDialog::SetVerificationCheckbox  
 Legt den Aktivierungszustand des Kontrollkästchens Überprüfung fest.  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bChecked`  
 `TRUE`die Überprüfung haben Sie das Kontrollkästchen ausgewählt, wenn die `CTaskDialog` wird angezeigt. `FALSE` haben die Überprüfung das Kontrollkästchen deaktiviert, wenn die `CTaskDialog` wird angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setverificationcheckboxtext"></a>CTaskDialog::SetVerificationCheckboxText  
 Legt den Text, der auf der rechten Seite des Kontrollkästchens Überprüfung angezeigt wird.  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strVerificationText`  
 Der Text, den neben dem Kontrollkästchen für die Überprüfung dieser Methode wird angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](diagnostic-services.md#ensure) Makro, wenn diese Instanz von der `CTaskDialog Class` wird bereits angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setwindowtitle"></a>CTaskDialog::SetWindowTitle  
 Definiert den Titel des der `CTaskDialog`.  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strWindowTitle`  
 Die neuen Titel für die `CTaskDialog`.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog #7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="showdialog"></a>CTaskDialog::ShowDialog  
 Erstellt und zeigt eine `CTaskDialog`.  
  
```  
static INT_PTR ShowDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast,  
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strContent`  
 Die Zeichenfolge, die für den Inhalt des verwenden die `CTaskDialog`.  
  
 [in] `strMainInstruction`  
 Die Anweisung von der `CTaskDialog`.  
  
 [in] `strTitle`  
 Der Titel des der `CTaskDialog`.  
  
 [in] `nIDCommandControlsFirst`  
 Die Zeichenfolgen-ID des ersten Befehls.  
  
 [in] `nIDCommandControlsLast`  
 Die Zeichenfolgen-ID des letzten Befehls.  
  
 [in] `nCommonButtons`  
 Eine Maske der Schaltflächen zum Hinzufügen der `CTaskDialog`.  
  
 [in] `nTaskDialogOptions`  
 Der Satz von Optionen für die `CTaskDialog`.  
  
 [in] `strFooter`  
 Das als Fußzeile zu verwendende Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die vom Benutzer vorgenommene Auswahl entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Diese statische Methode ermöglicht Ihnen die Erstellung eine Instanz von der `CTaskDialog Class` ohne explizites erstellen eine `CTaskDialog` Objekts in Ihrem Code. Da besteht keine `CTaskDialog` -Objekt, Sie können keine anderen Methoden von Aufrufen der `CTaskDialog` , wenn Sie diese Methode verwenden, um anzuzeigen eine `CTaskDialog` für den Benutzer.  
  
 Diese Methode erstellt Befehl Schaltflächen-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Zeichenfolgentabelle in der Ressourcendatei hat mehrere Zeichenfolgen mit zugeordneten IDs. Diese Methode fügt einen Befehl Button-Steuerelement für jeden gültigen Eintrag in der Zeichenfolgentabelle zwischen `nIDCommandControlsFirst` und `nCommandControlsLast`(einschließlich). Für diesen Befehl Schaltflächen-Steuerelemente, die Zeichenfolge in der Zeichenfolgentabelle ist die Beschriftung des Steuerelements, und die Zeichenfolgen-ID ist das Steuerelement-ID.  
  
 Finden Sie unter [CTaskDialog::SetOptions](#setoptions) eine Liste der gültigen Optionen.  
  
 Die `CTaskDialog` wird geschlossen, wenn der Benutzer eine allgemeine-Schaltfläche, ein Link-Steuerelement wählt, oder schließt die `CTaskDialog`. Der Rückgabewert ist der Bezeichner, der angibt, wie der Benutzer das Dialogfeld geschlossen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog Nr. 1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="taskdialogcallback"></a>CTaskDialog::TaskDialogCallback  
 Das Framework ruft diese Methode als Reaktion auf verschiedene Windows-Meldungen.  
  
```  
friend:  
HRESULT TaskDialogCallback(
    HWND hWnd,  
    UINT uNotification,  
    WPARAM wParam,  
    LPARAM lParam,  
    LONG_PTR dwRefData);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hwnd`  
 Ein Handle für die `m_hWnd` Struktur für die `CTaskDialog`.  
  
 [in] `uNotification`  
 Der Benachrichtigungscode, der die generierte Nachricht angibt.  
  
 [in] `wParam`  
 Weitere Informationen über die Nachricht.  
  
 [in] `lParam`  
 Weitere Informationen über die Nachricht.  
  
 [in] `dwRefData`  
 Ein Zeiger auf die `CTaskDialog` -Objekt, das die Rückrufnachricht gilt.  
  
### <a name="return-value"></a>Rückgabewert  
 Hängt von der jeweiligen Benachrichtigungscode. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des `TaskDialogCallback` bestimmte Nachricht verarbeitet, und ruft dann die entsprechende Methode von der [CTaskDialog Klasse](../../mfc/reference/ctaskdialog-class.md). Z. B. als Reaktion auf die `TDN_BUTTON_CLICKED` Nachricht `TaskDialogCallback` Aufrufe [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).  
  
 Die Werte für `wParam` und `lParam` richten sich nach den spezifischen generierte Nachricht. Es ist möglich, dass eines oder beide der folgenden Werte leer sein. Die folgende Tabelle enthält die Standard-Benachrichtigungen, die unterstützt werden und wie die Werte der `wParam` und `lParam` darstellen. Wenn Sie diese Methode in einer abgeleiteten Klasse überschreiben, sollten Sie die Rückrufcode für jede Nachricht in der folgenden Tabelle implementieren.  
  
|Benachrichtigungsmeldung|`wParam`-Wert|`lParam`-Wert|  
|--------------------------|--------------------|--------------------|  
|`TDN_CREATED`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_NAVIGATED`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_BUTTON_CLICKED`|Der Befehl Schaltflächensteuerelement ID.|Nicht verwendet.|  
|`TDN_HYPERLINK_CLICKED`|Nicht verwendet.|Ein [LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751) -Struktur, die den Link enthält.|  
|`TDN_TIMER`|Zeit in Millisekunden seit dem `CTaskDialog` erstellt wurde oder der Timer zurückgesetzt wurde.|Nicht verwendet.|  
|`TDN_DESTROYED`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_RADIO_BUTTON_CLICKED`|Die Optionsfeldgruppe Schaltfläche-ID.|Nicht verwendet.|  
|`TDN_DIALOG_CONSTRUCTED`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_VERIFICATION_CLICKED`|1, wenn Sie dieses Kontrollkästchen aktiviert ist, 0, wenn er nicht ist.|Nicht verwendet.|  
|`TDN_HELP`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_EXPANDO_BUTTON_CLICKED`|0, wenn der Bereich für die Erweiterung reduziert wird; Wert ungleich NULL, wenn die Erweiterung Text angezeigt wird.|Nicht verwendet.|  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Exemplarische Vorgehensweise: Hinzufügen eines CTaskDialog zu einer Anwendung](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)




