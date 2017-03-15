---
title: CTaskDialog-Klasse | Microsoft-Dokumentation
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 46de64825de9f824ce3d0a5d0c74b7cdc2352774
ms.lasthandoff: 02/24/2017

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
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Ein Befehlsschaltflächen-Steuerelement oder eine allgemeine Schaltfläche klickt programmgesteuert.|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Ein Optionsfeld klickt programmgesteuert.|  
|[CTaskDialog::DoModal](#domodal)|Zeigt das `CTaskDialog` an.|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Ruft die Anzahl der allgemeinen Schaltflächen zur Verfügung.|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Konvertiert einen Windows-Schaltfläche, um den allgemeinen Schaltflächentyp zugeordnete Standard der `CTaskDialog` Klasse.|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|Eine der häufig verwendeten Schaltfläche zugeordneten konvertiert die `CTaskDialog` Klasse, um eine standardmäßige Windows-Schaltfläche.|  
|[CTaskDialog::GetOptions](#getoptions)|Gibt Flags für die für dieses `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Gibt den ausgewählten Befehl Button-Steuerelement zurück.|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Gibt das ausgewählte Optionsfeld zurück.|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Ruft den Zustand des Kontrollkästchens Überprüfung.|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Bestimmt, ob ein Befehlsschaltflächen-Steuerelement oder eine allgemeine Schaltfläche aktiviert ist.|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Bestimmt, ob ein Optionsfeld aktiviert ist.|  
|[CTaskDialog::IsSupported](#issupported)|Bestimmt, ob der Computer mit der Anwendung unterstützt die `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Befehlsschaltfläche-Steuerelemente hinzugefügt mithilfe von Daten aus der Tabelle.|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|Optionsfelder hinzugefügt mithilfe von Daten aus der Tabelle.|  
|[CTaskDialog::NavigateTo](#navigateto)|Überträgt den Fokus auf ein anderes `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Das Framework ruft diese Methode, wenn der Benutzer auf eine Befehlsschaltfläche klickt.|  
|[CTaskDialog::OnCreate](#oncreate)|Das Framework ruft diese Methode nach dem Erstellen der `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](#ondestroy)|Das Framework ruft diese Methode auf, unmittelbar bevor es zerstört die `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Das Framework ruft diese Methode klickt der Benutzer auf die Schaltfläche "Erweitert".|  
|[CTaskDialog::OnHelp](#onhelp)|Das Framework ruft diese Methode auf, wenn der Benutzer die Hilfe anfordert.|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Das Framework ruft diese Methode, wenn der Benutzer auf einen Link klickt.|  
|[CTaskDialog::OnInit](#oninit)|Das Framework ruft diese Methode bei der `CTaskDialog` wird initialisiert.|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Das Framework ruft diese Methode auf, wenn der Benutzer den Fokus im Hinblick auf Steuerelemente bewegt, auf die `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Das Framework ruft diese Methode auf, wenn der Benutzer wählt ein Optionsfeld-Steuerelement aus.|  
|[CTaskDialog::OnTimer](#ontimer)|Das Framework ruft diese Methode auf, wenn der Zeitgeber abläuft.|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Das Framework ruft diese Methode klickt der Benutzer das Kontrollkästchen für die Überprüfung.|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Entfernt alle Command-Steuerelemente aus der `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Entfernt alle Optionsfelder aus der `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Aktualisiert ein Befehlsschaltflächen-Steuerelement auf die `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|Aktualisiert eine Teilmenge von allgemeinen Schaltflächen aktiviert werden und die Benutzerkontensteuerung erhöhte Rechte erforderlich.|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Fügt der Schaltflächen auf der `CTaskDialog`.|  
|[CTaskDialog::SetContent](#setcontent)|Aktualisiert den Inhalt der `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Gibt die Standard-Befehlsschaltfläche.|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Gibt die Standard-Optionsfeld.|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Passt die Breite der `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Aktualisiert die Erweiterungsbereich von der `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|Aktualisiert die Fußzeile-Symbol für die `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](#setfootertext)|Aktualisiert den Text in der Fußzeile der `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](#setmainicon)|Aktualisiert das Symbol von der `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Aktualisiert die Anweisung von der `CTaskDialog`.|  
|[CTaskDialog::SetOptions](#setoptions)|Konfiguriert die Optionen für die `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Konfiguriert eine Marquee-Leiste für die `CTaskDialog` und das Dialogfeld hinzugefügt.|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|Passt die Position der Statusanzeige.|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|Passt den Bereich der Statusanzeige an.|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|Legt den Zustand der Statusanzeige fest und zeigt sie auf der `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Aktiviert oder deaktiviert ein Optionsfeld.|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Legt den Aktivierungszustand des Kontrollkästchens Überprüfung fest.|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Legt den Text auf der rechten Seite des Kontrollkästchens Überprüfung fest.|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Legt den Titel der `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](#showdialog)|Erstellt und zeigt eine `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Das Framework ruft diese Reaktion auf verschiedene Windows-Meldungen.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|`m_aButtons`|Das Array der Befehlsschaltfläche-Steuerelemente für die `CTaskDialog`.|  
|`m_aRadioButtons`|Das Array von Optionsfeld-Steuerelementen für die `CTaskDialog`.|  
|`m_bVerified`|`TRUE`Gibt an, dass das Kontrollkästchen für die Überprüfung aktiviert ist. `FALSE` gibt an, dass es nicht.|  
|`m_footerIcon`|Das Symbol in der Fußzeile der `CTaskDialog`.|  
|`m_hWnd`|Ein Handle für das Fenster für die `CTaskDialog`.|  
|`m_mainIcon`|Das Symbol für die `CTaskDialog`.|  
|`m_nButtonDisabled`|Eine Maske, die gibt an, welche die allgemeine Schaltflächen werden deaktiviert.|  
|`m_nButtonElevation`|Eine Maske, die die allgemeine Schaltflächen angibt ist UAC erhöhte Rechte erforderlich.|  
|`m_nButtonId`|Die ID des ausgewählten Befehls Button-Steuerelements.|  
|`m_nCommonButton`|Eine Maske, die gibt an, welche Schaltflächen werden angezeigt, auf die `CTaskDialog`.|  
|`m_nDefaultCommandControl`|Die ID der Schaltfläche steuern, die ausgewählt wird, wenn die `CTaskDialog` wird angezeigt.|  
|`m_nDefaultRadioButton`|Die ID des Optionsfelds steuern, die ausgewählt wird, wenn die `CTaskDialog` wird angezeigt.|  
|`m_nFlags`|Eine Maske, die gibt die Optionen für die `CTaskDialog`.|  
|`m_nProgressPos`|Die aktuelle Position für die Statusanzeige.  Dabei muss es sich um einen Wert zwischen `m_nProgressRangeMin` und `m_nProgressRangeMax` handeln.|  
|`m_nProgressRangeMax`|Der maximale Wert für die Statusanzeige.|  
|`m_nProgressRangeMin`|Der Mindestwert für die Statusanzeige.|  
|`m_nProgressState`|Der Status der Statusanzeige. Weitere Informationen finden Sie unter [CTaskDialog::SetProgressBarState](#setprogressbarstate).|  
|`m_nRadioId`|Die ID des dem ausgewählten Optionsfeld-Steuerelement.|  
|`m_nWidth`|Die Breite der `CTaskDialog` in Pixel.|  
|`m_strCollapse`|Die Zeichenfolge der `CTaskDialog` rechts neben dem Feld Erweiterung zeigt an, wenn die erweiterte Informationen ausgeblendet ist.|  
|`m_strContent`|Die Inhaltszeichenfolge der `CTaskDialog`.|  
|`m_strExpand`|Die Zeichenfolge der `CTaskDialog` rechts neben dem Feld Erweiterung angezeigt, wenn die erweiterte Informationen angezeigt werden.|  
|`m_strFooter`|Der Fußzeile der `CTaskDialog`.|  
|`m_strInformation`|Die erweiterten Informationen für die `CTaskDialog`.|  
|`m_strMainInstruction`|Die Anweisung von der `CTaskDialog`.|  
|`m_strTitle`|Der Titel der `CTaskDialog`.|  
|`m_strVerification`|Die Zeichenfolge, die die `CTaskDialog` rechts neben das Kontrollkästchen Überprüfung angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CTaskDialog` -Klasse ersetzt das standardmäßige Windows-Meldungsfeld und verfügt über zusätzliche Funktionen wie neue Steuerelemente zum Sammeln von Informationen vom Benutzer. Diese Klasse ist in der MFC-Bibliothek in [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]. Die `CTaskDialog` steht ab [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. In früheren Versionen von Windows können nicht angezeigt. die `CTaskDialog` Objekt. Verwendung `CTaskDialog::IsSupported` zur Laufzeit bestimmt, ob der aktuelle Benutzer das Aufgabendialogfeld angezeigt werden kann. Das standardmäßige Windows-Meldungsfeld wird weiterhin unterstützt [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  
  
 Die `CTaskDialog` steht nur beim Erstellen der Anwendung mithilfe der Unicode-Bibliothek.  
  
 Die `CTaskDialog` verfügt über zwei verschiedene Konstruktoren. Ein Konstruktor können Sie zwei Schaltflächen und maximal sechs regulären Schaltflächen-Steuerelementen an. Sie können weitere Schaltflächen hinzufügen, nach dem Erstellen der `CTaskDialog`. Der zweite Konstruktor keine Befehlsschaltflächen unterstützt, aber Sie können eine unbegrenzte Anzahl von regulären Schaltflächen-Steuerelementen hinzufügen. Weitere Informationen zu Konstruktoren, finden Sie unter [CTaskDialog::CTaskDialog](#ctaskdialog).  
  
 Die folgende Abbildung zeigt ein Beispiel für `CTaskDialog` um den Speicherort der einige Steuerelemente zu veranschaulichen.  
  
 ![Beispiel für CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
Beispiel für CTaskDialog  
  
## <a name="requirements"></a>Anforderungen  
 **Erforderliche Betriebssystem:**[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
 **Header:** afxtaskdialog.h  
  
##  <a name="a-nameaddcommandcontrola--ctaskdialogaddcommandcontrol"></a><a name="addcommandcontrol"></a>CTaskDialog::AddCommandControl  
 Fügt ein neuen Befehl Button-Steuerelement auf die `CTaskDialog`.  
  
```  
void AddCommandControl(
    int nCommandControlID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die ID für den Befehl Steuerelement.  
  
 [in] `strCaption`  
 Die Zeichenfolge, die die `CTaskDialog` zeigt dem Benutzer an. Verwenden Sie diese Zeichenfolge, um den Zweck des Befehls erläutern.  
  
 [in] `bEnabled`  
 Ein boolescher Parameter, der angibt, ob die neue Schaltfläche aktiviert oder deaktiviert ist.  
  
 [in] `bRequiresElevation`  
 Ein boolescher Parameter, der angibt, ob ein Befehl erhöhte Rechte erforderlich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die `CTaskDialog Class` kann eine unbegrenzte Anzahl von Befehlsschaltfläche-Steuerelemente anzuzeigen. Jedoch, wenn ein `CTaskDialog` zeigt jede Befehlsschaltfläche gesteuert, es kann bis zu sechs Schaltflächen angezeigt. Wenn eine `CTaskDialog` wurde keine Schaltfläche Befehlssteuerelemente, es kann eine unbegrenzte Anzahl von Schaltflächen angezeigt.  
  
 Bei der Auswahl einer Befehlsschaltfläche, die `CTaskDialog` geschlossen wird. Wenn die Anwendung zeigt das Dialogfeld mit [CTaskDialog::DoModal](#domodal), `DoModal` gibt die `nCommandControlID` des ausgewählten Befehls Button-Steuerelements.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-nameaddradiobuttona--ctaskdialogaddradiobutton"></a><a name="addradiobutton"></a>CTaskDialog::AddRadioButton  
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
 Die Zeichenfolge, die die `CTaskDialog` neben dem Optionsfeld angezeigt.  
  
 [in] `bEnabled`  
 Ein boolescher Parameter, der angibt, ob das Optionsfeld aktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Optionsfelder für die [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) ermöglichen es Ihnen, Informationen vom Benutzer zu erfassen. Verwenden Sie die Funktion [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) um zu bestimmen, welches Optionsfeld ausgewählt ist.  
  
 Die `CTaskDialog` nicht erfordert, dass der `nRadioButtonID` Parameter für jedes Optionsfeld eindeutig sind. Allerdings können Sie unerwartetes Verhalten auftreten, wenn Sie keinen unterschiedlichen Bezeichner für jedes Optionsfeld verwenden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-nameclickcommandcontrola--ctaskdialogclickcommandcontrol"></a><a name="clickcommandcontrol"></a>CTaskDialog::ClickCommandControl  
 Ein Befehlsschaltflächen-Steuerelement oder eine allgemeine Schaltfläche klickt programmgesteuert.  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die Befehls-ID des Steuerelements klicken.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode generiert, die Windows-Meldung `TDM_CLICK_BUTTON`.  
  
##  <a name="a-nameclickradiobuttona--ctaskdialogclickradiobutton"></a><a name="clickradiobutton"></a>CTaskDialog::ClickRadioButton  
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
  
##  <a name="a-namectaskdialoga--ctaskdialogctaskdialog"></a><a name="ctaskdialog"></a>CTaskDialog::CTaskDialog  
 Erstellt eine Instanz der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md).  
  
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
 Die Zeichenfolge, für den Inhalt der `CTaskDialog`.  
  
 [in] `strMainInstruction`  
 Die Anweisung von der `CTaskDialog`.  
  
 [in] `strTitle`  
 Der Titel der `CTaskDialog`.  
  
 [in] `nCommonButtons`  
 Maske die allgemeinen Schaltflächen zum Hinzufügen der `CTaskDialog`.  
  
 [in] `nTaskDialogOptions`  
 Der Satz von Optionen für die `CTaskDialog`.  
  
 [in] `strFooter`  
 Die Zeichenfolge, die als Fußzeile verwenden.  
  
 [in] `nIDCommandControlsFirst`  
 Die Zeichenfolgen-ID des ersten Befehls.  
  
 [in] `nIDCommandControlsLast`  
 Die Zeichenfolgen-ID des letzten Befehls.  
  
### <a name="remarks"></a>Hinweise  
 Es gibt zwei Möglichkeiten, die Sie hinzufügen, können eine `CTaskDialog` für Ihre Anwendung. Die erste Möglichkeit ist die Verwendung einer der Konstruktoren zum Erstellen einer `CTaskDialog` und mithilfe [CTaskDialog::DoModal](#domodal). Die zweite Möglichkeit ist die Verwendung die statische Funktion [CTaskDialog::ShowDialog](#showdialog), die Sie anzeigen können eine `CTaskDialog` ohne explizite Erstellung einer `CTaskDialog` Objekt.  
  
 Der zweite Konstruktor erstellt Befehlsschaltfläche-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Tabelle in der Ressourcendatei hat mehrere Zeichenfolgen mit zugeordneten Zeichenfolgen-IDs. Diese Methode fügt ein Befehlsschaltflächen-Steuerelement für jeden gültigen Eintrag in der Zeichenfolgentabelle zwischen `nIDCommandControlsFirst` und `nCommandControlsLast`, inklusive. Für diese Befehlsschaltfläche-Steuerelemente die Zeichenfolge in der Tabelle ist die Beschriftung des Steuerelements und die Zeichenfolgen-ID des Steuerelements.  
  
 Finden Sie unter [CTaskDialog::SetOptions](#setoptions) eine Liste der gültigen Optionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namedomodala--ctaskdialogdomodal"></a><a name="domodal"></a>CTaskDialog::DoModal  
 Zeigt die `CTaskDialog` und gebunden.  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hParent`  
 Das übergeordnete Fenster für die `CTaskDialog`.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die die vom Benutzer vorgenommene Auswahl entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Zeigt diese Instanz die [CTaskDialog](../../mfc/reference/ctaskdialog-class.md). Die Anwendung und wartet, bis der Benutzer das Dialogfeld zu schließen.  
  
 Die `CTaskDialog` wird geschlossen, wenn der Benutzer eine allgemeine Schaltfläche, ein Link-Steuerelement wählt, oder schließt das `CTaskDialog`. Der Rückgabewert ist der Bezeichner, der angibt, wie der Benutzer das Dialogfeld geschlossen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namegetcommonbuttoncounta--ctaskdialoggetcommonbuttoncount"></a><a name="getcommonbuttoncount"></a>CTaskDialog::GetCommonButtonCount  
 Ruft die Anzahl der Schaltflächen ab.  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der allgemeinen Schaltflächen zur Verfügung.  
  
### <a name="remarks"></a>Hinweise  
 Die allgemeinen Schaltflächen sind Schaltflächen, die Sie zur Verfügung stellen [CTaskDialog::CTaskDialog](#ctaskdialog). Die [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) Schaltflächen am unteren Rand des Dialogfelds angezeigt.  
  
 Die Liste der Schaltflächen wird in CommCtrl.h bereitgestellt.  
  
##  <a name="a-namegetcommonbuttonflaga--ctaskdialoggetcommonbuttonflag"></a><a name="getcommonbuttonflag"></a>CTaskDialog::GetCommonButtonFlag  
 Konvertiert einen Windows-Schaltfläche, um den allgemeinen Schaltflächentyp zugeordnete Standard der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md).  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nButtonId`  
 Der standardmäßige Wert der Windows-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des entsprechenden `CTaskDialog` allgemeine Schaltfläche. Wenn keine entsprechende allgemeine Schaltfläche vorhanden ist, gibt diese Methode 0 zurück.  
  
##  <a name="a-namegetcommonbuttonida--ctaskdialoggetcommonbuttonid"></a><a name="getcommonbuttonid"></a>CTaskDialog::GetCommonButtonId  
 Konvertiert eine der allgemeinen Schaltflächentypen mit den [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) mit einer standardmäßigen Windows-Schaltfläche.  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFlag`  
 Der allgemeine Schaltflächentyp zugeordnet der `CTaskDialog` Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert der entsprechenden Windows-Standardschaltfläche. Wenn keine entsprechenden Windows-Schaltfläche vorhanden ist, gibt die Methode 0 zurück.  
  
##  <a name="a-namegetoptionsa--ctaskdialoggetoptions"></a><a name="getoptions"></a>CTaskDialog::GetOptions  
 Gibt Flags für die für dieses `CTaskDialog`.  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Flags für die `CTaskDialog`.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den Optionen für die [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md), finden Sie unter [CTaskDialog::SetOptions](#setoptions).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namegetselectedcommandcontrolida--ctaskdialoggetselectedcommandcontrolid"></a><a name="getselectedcommandcontrolid"></a>CTaskDialog::GetSelectedCommandControlID  
 Gibt den ausgewählten Befehl Button-Steuerelement zurück.  
  
```  
int GetSelectedCommandControlID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ID der momentan ausgewählten Befehl Button-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen keinen verwenden Sie diese Methode zum Abrufen der ID der Schaltfläche, die der Benutzer ausgewählt hat. Diese ID wird zurückgegeben, entweder durch [CTaskDialog::DoModal](#domodal) oder [CTaskDialog::ShowDialog](#showdialog).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-namegetselectedradiobuttonida--ctaskdialoggetselectedradiobuttonid"></a><a name="getselectedradiobuttonid"></a>CTaskDialog::GetSelectedRadioButtonID  
 Gibt das ausgewählte Optionsfeld zurück.  
  
```  
int GetSelectedRadioButtonID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ID des ausgewählten Optionsfeldes.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode verwenden, nachdem der Benutzer das Dialogfeld zum Abrufen der ausgewählten Optionsfeld wird geschlossen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namegetverificationcheckboxstatea--ctaskdialoggetverificationcheckboxstate"></a><a name="getverificationcheckboxstate"></a>CTaskDialog::GetVerificationCheckboxState  
 Ruft den Zustand des Kontrollkästchens Überprüfung.  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Kontrollkästchen aktiviert ist, `FALSE` ist dies nicht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&5;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="a-nameiscommandcontrolenableda--ctaskdialogiscommandcontrolenabled"></a><a name="iscommandcontrolenabled"></a>CTaskDialog::IsCommandControlEnabled  
 Bestimmt, ob ein Befehlsschaltflächen-Steuerelement oder eine Schaltfläche aktiviert ist.  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die ID des Befehlsschaltfläche-Steuerelement oder eine Schaltfläche zum Testen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Steuerelement aktiviert ist, `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode verwenden, bestimmen die Verfügbarkeit von sowohl Befehlsschaltfläche-Steuerelemente und die allgemeinen Schaltflächen von der `CTaskDialog Class`.  
  
 Wenn `nCommandControlID` ist kein gültiger Bezeichner für die eine gemeinsame `CTaskDialog` Schaltfläche oder eine Befehlsschaltfläche, löst diese Methode eine Ausnahme aus.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-nameisradiobuttonenableda--ctaskdialogisradiobuttonenabled"></a><a name="isradiobuttonenabled"></a>CTaskDialog::IsRadioButtonEnabled  
 Bestimmt, ob ein Optionsfeld aktiviert ist.  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID des Optionsfelds zu testen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Optionsfeld aktiviert ist, `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nRadioButtonID` ist kein gültiger Bezeichner für ein Optionsfeld, löst diese Methode eine Ausnahme aus.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-nameissupporteda--ctaskdialogissupported"></a><a name="issupported"></a>CTaskDialog::IsSupported  
 Bestimmt, ob der Computer mit der Anwendung unterstützt die `CTaskDialog`.  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Computer unterstützt die `CTaskDialog`; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie um zur Laufzeit zu bestimmen, ob es sich bei der Computer mit der Anwendung unterstützt die `CTaskDialog Class`. Wenn der Computer nicht unterstützt wird die `CTaskDialog`, sollten Sie eine andere Methode für die Kommunikation von Informationen für den Benutzer bereitstellen. Die Anwendung stürzt ab, wenn versucht wird, verwenden Sie eine `CTaskDialog` auf einem Computer, der nicht unterstützt wird die `CTaskDialog` Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#1;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="a-nameloadcommandcontrolsa--ctaskdialogloadcommandcontrols"></a><a name="loadcommandcontrols"></a>CTaskDialog::LoadCommandControls  
 Befehlsschaltfläche-Steuerelemente hinzugefügt mithilfe von Daten aus der Tabelle.  
  
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
 Diese Methode erstellt die Befehlsschaltfläche-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Tabelle in der Ressourcendatei hat mehrere Zeichenfolgen mit zugeordneten Zeichenfolgen-IDs. Neue Befehlsschaltfläche-Steuerelemente hinzugefügt, die mit dieser Methode verwenden Sie die Zeichenfolge für die Beschriftung des Steuerelements und die Zeichenfolgen-ID für das Steuerelement-ID Der Bereich der ausgewählten Zeichenfolgen erfolgt über `nIDCommandControlsFirst` und `nCommandControlsLast`, inklusive. Liegt ein leerer Eintrag im Bereich, wird die Methode ein Befehlsschaltflächen-Steuerelement für diesen Eintrag nicht hinzufügen.  
  
 Standardmäßig werden neue Befehlsschaltfläche-Steuerelemente aktiviert sind und erfordern keine Erhöhung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-nameloadradiobuttonsa--ctaskdialogloadradiobuttons"></a><a name="loadradiobuttons"></a>CTaskDialog::LoadRadioButtons  
 Optionsfeld-Steuerelementen hinzugefügt mithilfe von Daten aus der Tabelle.  
  
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
 Diese Methode erstellt die Optionsfelder mit Daten aus der Ressourcendatei der Anwendung. Die Tabelle in der Ressourcendatei hat mehrere Zeichenfolgen mit zugeordneten Zeichenfolgen-IDs. Neue Optionsfelder, die mit dieser Methode hinzugefügt und verwenden Sie die Zeichenfolge für das Optionsfeld Beschriftung und die Zeichenfolgen-ID für das Optionsfeld-ID. Der Bereich der ausgewählten Zeichenfolgen erfolgt über `nIDRadioButtonsFirst` und `nRadioButtonsLast`, inklusive. Liegt ein leerer Eintrag im Bereich, wird die Methode ein Optionsfeld für den Eintrag nicht hinzufügen.  
  
 Standardmäßig sind neue Optionsfelder aktiviert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namenavigatetoa--ctaskdialognavigateto"></a><a name="navigateto"></a>CTaskDialog::NavigateTo  
 Überträgt den Fokus auf ein anderes `CTaskDialog`.  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `oTaskDialog`  
 Die `CTaskDialog` , die den Fokus erhält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode blendet das aktuelle `CTaskDialog` Anzeige der `oTaskDialog`. Die `oTaskDialog` wird angezeigt, am gleichen Speicherort wie die aktuelle `CTaskDialog`.  
  
##  <a name="a-nameoncommandcontrolclicka--ctaskdialogoncommandcontrolclick"></a><a name="oncommandcontrolclick"></a>CTaskDialog::OnCommandControlClick  
 Das Framework ruft diese Methode, wenn der Benutzer auf eine Befehlsschaltfläche klickt.  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die ID der Befehlsschaltfläche, die der Benutzer ausgewählt hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameoncreatea--ctaskdialogoncreate"></a><a name="oncreate"></a>CTaskDialog::OnCreate  
 Das Framework ruft diese Methode nach dem Erstellen der `CTaskDialog`.  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameondestroya--ctaskdialogondestroy"></a><a name="ondestroy"></a>CTaskDialog::OnDestroy  
 Das Framework ruft diese Methode auf, unmittelbar bevor es zerstört die `CTaskDialog`.  
  
```  
virtual HRESULT OnDestroy();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameonexpandbuttonclicka--ctaskdialogonexpandbuttonclick"></a><a name="onexpandbuttonclick"></a>CTaskDialog::OnExpandButtonClick  
 Das Framework ruft diese Methode klickt der Benutzer auf die Schaltfläche "Erweitert".  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bExpanded`  
 Ein Wert ungleich Null gibt an, dass die zusätzliche Informationen angezeigt werden. 0 gibt an, dass die zusätzliche Informationen ausgeblendet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameonhelpa--ctaskdialogonhelp"></a><a name="onhelp"></a>CTaskDialog::OnHelp  
 Das Framework ruft diese Methode auf, wenn der Benutzer die Hilfe anfordert.  
  
```  
virtual HRESULT OnHelp();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameonhyperlinkclicka--ctaskdialogonhyperlinkclick"></a><a name="onhyperlinkclick"></a>CTaskDialog::OnHyperlinkClick  
 Das Framework ruft diese Methode, wenn der Benutzer auf einen Link klickt.  
  
```  
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strHref`  
 Die Zeichenfolge, die den Hyperlink darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) vor der Rückgabe `S_OK`.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameoninita--ctaskdialogoninit"></a><a name="oninit"></a>CTaskDialog::OnInit  
 Das Framework ruft diese Methode bei der `CTaskDialog` wird initialisiert.  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameonnavigatepagea--ctaskdialogonnavigatepage"></a><a name="onnavigatepage"></a>CTaskDialog::OnNavigatePage  
 Das Framework ruft diese Methode als Antwort auf die [CTaskDialog::NavigateTo](#navigateto) Methode.  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameonradiobuttonclicka--ctaskdialogonradiobuttonclick"></a><a name="onradiobuttonclick"></a>CTaskDialog::OnRadioButtonClick  
 Das Framework ruft diese Methode auf, wenn der Benutzer wählt ein Optionsfeld-Steuerelement aus.  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID der das RadioButton-Steuerelement, das der Benutzer geklickt hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameontimera--ctaskdialogontimer"></a><a name="ontimer"></a>CTaskDialog::OnTimer  
 Das Framework ruft diese Methode auf, wenn der Zeitgeber abläuft.  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lTime`  
 Zeit in Millisekunden seit dem `CTaskDialog` erstellt wurde oder der Timer zurückgesetzt wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameonverificationcheckboxclicka--ctaskdialogonverificationcheckboxclick"></a><a name="onverificationcheckboxclick"></a>CTaskDialog::OnVerificationCheckboxClick  
 Das Framework ruft diese Methode klickt der Benutzer das Kontrollkästchen für die Überprüfung.  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bChecked`  
 `TRUE`Gibt an, dass das Kontrollkästchen für die Überprüfung aktiviert ist. `FALSE` gibt an, dass es nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt `S_OK` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameremoveallcommandcontrolsa--ctaskdialogremoveallcommandcontrols"></a><a name="removeallcommandcontrols"></a>CTaskDialog::RemoveAllCommandControls  
 Entfernt alle der Befehlsschaltfläche-Steuerelemente aus der `CTaskDialog`.  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-nameremoveallradiobuttonsa--ctaskdialogremoveallradiobuttons"></a><a name="removeallradiobuttons"></a>CTaskDialog::RemoveAllRadioButtons  
 Entfernt alle Optionsfelder aus der `CTaskDialog`.  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namesetcommandcontroloptionsa--ctaskdialogsetcommandcontroloptions"></a><a name="setcommandcontroloptions"></a>CTaskDialog::SetCommandControlOptions  
 Aktualisiert ein Befehlsschaltflächen-Steuerelement auf die `CTaskDialog`.  
  
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
 Ein boolescher Parameter, der angibt, ob die angegebene Befehlsschaltfläche erhöhte Rechte erforderlich sind.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie angeben, ob ein Befehlsschaltflächen-Steuerelement aktiviert ist oder erforderlich ist, nachdem er hinzugefügt wurde der `CTaskDialog Class`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-namesetcommonbuttonoptionsa--ctaskdialogsetcommonbuttonoptions"></a><a name="setcommonbuttonoptions"></a>CTaskDialog::SetCommonButtonOptions  
 Aktualisiert eine Teilmenge von allgemeinen Schaltflächen aktiviert werden und Benutzerkontensteuerung erhöhte Rechte erforderlich.  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nDisabledButtonMask`  
 Eine Maske für die allgemeine Schaltflächen deaktivieren.  
  
 [in] `nElevationButtonMask`  
 Eine Maske für die allgemeinen Schaltflächen, die erhöhte Rechte erfordern.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die allgemeinen Schaltflächen verfügbar festlegen, mit einer Instanz von der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) wird mit dem Konstruktor [CTaskDialog::CTaskDialog](#ctaskdialog) und die Methode [CTaskDialog::SetCommonButtons](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions`unterstützt keine neue allgemeine Schaltflächen hinzufügen.  
  
 Wenn Sie diese Methode verwenden, deaktivieren oder erhöhen eine allgemeine Schaltfläche, die für diese nicht verfügbar ist `CTaskDialog`, löst diese Methode eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro.  
  
 Mit dieser Methode können Sie eine Taste, die zur Verfügung steht, die die `CTaskDialog` jedoch nicht in der `nDisabledButtonMask`, selbst wenn sie zuvor deaktiviert war. Diese Methode erhöhte Rechte auf ähnliche Weise behandelt: Zeichnet allgemeine Schaltflächen nicht erhöhte Rechte erforderlich sind, die allgemeine Schaltfläche ist verfügbar, aber nicht in enthalten `nElevationButtonMask`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&6;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="a-namesetcommonbuttonsa--ctaskdialogsetcommonbuttons"></a><a name="setcommonbuttons"></a>CTaskDialog::SetCommonButtons  
 Fügt der Schaltflächen auf der `CTaskDialog`.  
  
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
 Eine Maske der Schaltflächen, um Sie zu deaktivieren.  
  
 [in] `nElevationButtonMask`  
 Eine Maske der Schaltflächen, die erhöhte Rechte erfordern.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode nach das Anzeigefenster für diese Instanz von Aufrufen der `CTaskDialog Class` wird erstellt. Wenn Sie dies tun, löst diese Methode eine Ausnahme aus.  
  
 Die Schaltflächen erkennbar `nButtonMask` überschreiben alle allgemeinen Schaltflächen, die zuvor hinzugefügt wurde der `CTaskDialog`. Nur die Schaltflächen im angegebenen `nButtonMask` verfügbar sind.  
  
 Wenn entweder `nDisabledButtonMask` oder `nElevationButtonMask` enthalten eine Schaltfläche, der nicht `nButtonMask`, löst diese Methode eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro.  
  
 Standardmäßig werden alle Schaltflächen aktiviert sind und erfordern keine Erhöhung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&6;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="a-namesetcontenta--ctaskdialogsetcontent"></a><a name="setcontent"></a>CTaskDialog::SetContent  
 Aktualisiert den Inhalt der `CTaskDialog`.  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strContent`  
 Die Zeichenfolge, die dem Benutzer angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Der Inhalt der `CTaskDialog Class` ist der Text, der dem Benutzer im Hauptteil des Dialogfelds angezeigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetdefaultcommandcontrola--ctaskdialogsetdefaultcommandcontrol"></a><a name="setdefaultcommandcontrol"></a>CTaskDialog::SetDefaultCommandControl  
 Gibt die Standard-Befehlsschaltfläche.  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandControlID`  
 Die ID der Befehlsschaltfläche das Standardabonnement sein soll.  
  
### <a name="remarks"></a>Hinweise  
 Schaltflächen-Steuerelement der Standardwert ist das Steuerelement, ist ausgewählt, wenn die `CTaskDialog` für den Benutzer zum ersten Mal angezeigt wird.  
  
 Diese Methode löst eine Ausnahme aus, wenn die Befehlsschaltfläche, die durch angegebene gefunden werden kann `nCommandControlID`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#2;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="a-namesetdefaultradiobuttona--ctaskdialogsetdefaultradiobutton"></a><a name="setdefaultradiobutton"></a>CTaskDialog::SetDefaultRadioButton  
 Gibt die Standard-Optionsfeld.  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRadioButtonID`  
 Die ID des Optionsfelds das Standardabonnement sein soll.  
  
### <a name="remarks"></a>Hinweise  
 Das Standard-Optionsfeld ist die Schaltfläche ausgewählt, wenn die `CTaskDialog` für den Benutzer zum ersten Mal angezeigt wird.  
  
 Diese Methode löst eine Ausnahme aus, wenn das Optionsfeld angegebenen gefunden `nRadioButtonID`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namesetdialogwidtha--ctaskdialogsetdialogwidth"></a><a name="setdialogwidth"></a>CTaskDialog::SetDialogWidth  
 Passt die Breite der `CTaskDialog`.  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nWidth`  
 Die Breite des Dialogfelds in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `nWidth` muss größer als oder gleich 0 sein. Andernfalls löst diese Methode eine Ausnahme aus.  
  
 Wenn `nWidth` 0 ist, legt diese Methode das Dialogfeld auf den Standardwert festgelegt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetexpansionareaa--ctaskdialogsetexpansionarea"></a><a name="setexpansionarea"></a>CTaskDialog::SetExpansionArea  
 Aktualisiert die Erweiterungsbereich von der `CTaskDialog`.  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strExpandedInformation`  
 Die Zeichenfolge, die die `CTaskDialog` im Hauptteil des Dialogfelds angezeigt wird, klickt der Benutzer auf die Erweiterungsschaltfläche.  
  
 [in] `strCollapsedLabel`  
 Die Zeichenfolge, die die `CTaskDialog` neben die Erweiterungsschaltfläche angezeigt wird, wenn der erweiterte Bereich reduziert ist.  
  
 [in] `strExpandedLabel`  
 Die Zeichenfolge, die die `CTaskDialog` neben die Erweiterungsschaltfläche angezeigt wird, wenn der erweiterte Bereich angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Erweiterungsbereich der `CTaskDialog Class` ermöglicht es Ihnen, zusätzliche Informationen für den Benutzer bereitstellen. Der Erweiterungsbereich befindet sich in den Hauptteil der `CTaskDialog`befindet sich direkt unterhalb der Titel und Inhalt der Zeichenfolge.  
  
 Wenn die `CTaskDialog` steht an erster Stelle angezeigt, es wird nicht die erweiterte Informationen angezeigt und setzt `strCollapsedLabel` neben der Erweiterungsschaltfläche. Klickt der Benutzer auf die Erweiterungsschaltfläche der `CTaskDialog` zeigt `strExpandedInformation` und ändert die Bezeichnung `strExpandedLabel`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetfootericona--ctaskdialogsetfootericon"></a><a name="setfootericon"></a>CTaskDialog::SetFooterIcon  
 Aktualisiert das Symbol Fußzeile, der die `CTaskDialog`.  
  
```  
void SetFooterIcon(HICON hFooterIcon);  
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hFooterIcon`  
 Das neue Symbol für die `CTaskDialog`.  
  
 [in] `lpszFooterIcon`  
 Das neue Symbol für die `CTaskDialog`.  
  
### <a name="remarks"></a>Hinweise  
 Der Fußzeile angezeigt am unteren Rand der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md). Sie können Fußzeilentext zugeordnet. Sie können den Fußzeilentext mit ändern [CTaskDialog::SetFooterText](#setfootertext).  
  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro Wenn die `CTaskDialog` wird angezeigt, oder der Eingabeparameter ist `NULL`.  
  
 Ein `CTaskDialog` akzeptiert nur ein `HICON` oder `LPCWSTR` als Fußzeile-Symbol. Dies wird durch Festlegen der Option konfiguriert `TDF_USE_HICON_FOOTER` im Konstruktor oder [CTaskDialog::SetOptions](#setoptions). In der Standardeinstellung die `CTaskDialog` für die Verwendung konfiguriert `LPCWSTR` als Eingabetyp für die Fußzeile-Symbol. Diese Methode generiert eine Ausnahme aus, wenn Sie versuchen, das Symbol mit dem unzulässigen Typ festzulegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetfootertexta--ctaskdialogsetfootertext"></a><a name="setfootertext"></a>CTaskDialog::SetFooterText  
 Aktualisiert den Text in der Fußzeile der `CTaskDialog`.  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strFooterText`  
 Der neue Text für die Fußzeile.  
  
### <a name="remarks"></a>Hinweise  
 Das Footer-Symbol wird neben den Footertext am unteren Rand der `CTaskDialog`. Sie können das Symbol Fußzeile mit ändern [CTaskDialog::SetFooterIcon](#setfootericon).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetmainicona--ctaskdialogsetmainicon"></a><a name="setmainicon"></a>CTaskDialog::SetMainIcon  
 Aktualisiert das Symbol von der `CTaskDialog`.  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMainIcon`  
 Das Symbol neu.  
  
 [in] `lpszMainIcon`  
 Das Symbol neu.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro Wenn die `CTaskDialog` wird angezeigt, oder der Eingabeparameter ist `NULL`.  
  
 Ein `CTaskDialog` akzeptiert nur ein `HICON` oder `LPCWSTR` als Haupt-Symbol. Sie können dies konfigurieren, indem die `TDF_USE_HICON_MAIN` Option im Konstruktor oder im der [CTaskDialog::SetOptions](#setoptions) Methode. In der Standardeinstellung die `CTaskDialog` für die Verwendung konfiguriert `LPCWSTR` als Eingabetyp für das Symbol. Diese Methode generiert eine Ausnahme aus, wenn Sie versuchen, das Symbol mit dem unzulässigen Typ festzulegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetmaininstructiona--ctaskdialogsetmaininstruction"></a><a name="setmaininstruction"></a>CTaskDialog::SetMainInstruction  
 Aktualisiert die Anweisung von der `CTaskDialog`.  
  
```  
void SetMainInstruction(const CString& strInstructions);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strInstructions`  
 Die neue Anweisung.  
  
### <a name="remarks"></a>Hinweise  
 Die Anweisung von der `CTaskDialog Class` Text in großer Schriftart fett formatiert angezeigt wird. Die Datei befindet sich im Dialogfeld unterhalb der Titelleiste.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetoptionsa--ctaskdialogsetoptions"></a><a name="setoptions"></a>CTaskDialog::SetOptions  
 Konfiguriert die Optionen für die `CTaskDialog`.  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOptionFlag`  
 Der Satz von Flags mit der `CTaskDialog`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löscht die aktuellen Optionen für die `CTaskDialog`. Um die aktuellen Optionen zu erhalten, müssen Sie diese zuerst Abrufen mit [CTaskDialog::GetOptions](#getoptions) und kombinieren Sie diese mit den Optionen, die Sie festlegen möchten.  
  
 In der folgenden Tabelle werden alle gültigen Optionen aufgelistet.  
  
 `TDF_ENABLE_HYPERLINKS`  
 Ermöglicht die Links in der `CTaskDialog`.  
  
 `TDF_USE_HICON_MAIN`  
 Konfiguriert die `CTaskDialog` verwenden eine `HICON` für das Symbol. Die Alternative ist die Verwendung einer `LPCWSTR`.  
  
 `TDF_USE_HICON_FOOTER`  
 Konfiguriert die `CTaskDialog` verwenden eine `HICON` für die Fußzeile-Symbol. Die Alternative ist die Verwendung einer `LPCWSTR`.  
  
 `TDF_ALLOW_DIALOG_CANCELLATION`  
 Ermöglicht dem Benutzer, schließen Sie die `CTaskDialog` mithilfe der Tastatur oder über das Symbol in der Ecke oben rechts im Dialogfeld selbst wenn die **Abbrechen** Schaltfläche ist nicht aktiviert. Wenn dieses Flag nicht festgelegt ist und die **Abbrechen** Schaltfläche ist nicht aktiviert, der Benutzer kann nicht mithilfe von Alt + F4 drücken die ESC-Taste, um das Dialogfeld schließen oder der Titelleiste Schließ-Schaltfläche.  
  
 `TDF_USE_COMMAND_LINKS`  
 Konfiguriert die `CTaskDialog` Befehlsschaltfläche-Steuerelemente verwenden.  
  
 `TDF_USE_COMMAND_LINKS_NO_ICON`  
 Konfiguriert die `CTaskDialog` Befehlsschaltfläche-Steuerelemente verwenden, ohne dass ein Symbol neben dem Steuerelement angezeigt. `TDF_USE_COMMAND_LINKS` überschreibt `TDF_USE_COMMAND_LINKS_NO_ICON`.  
  
 `TDF_EXPAND_FOOTER_AREA`  
 Gibt an, dass die Erweiterungsbereich derzeit erweitert ist.  
  
 `TDF_EXPANDED_BY_DEFAULT`  
 Bestimmt, ob die Erweiterungsbereich standardmäßig erweitert wird.  
  
 `TDF_VERIFICATION_FLAG_CHECKED`  
 Gibt an, dass das Kontrollkästchen Überprüfung derzeit ausgewählt ist.  
  
 `TDF_SHOW_PROGRESS_BAR`  
 Konfiguriert die `CTaskDialog` eine Statusanzeige angezeigt.  
  
 `TDF_SHOW_MARQUEE_PROGRESS_BAR`  
 Die Statusanzeige, um eine Marquee-Statusanzeige wird konfiguriert. Wenn Sie diese Option aktivieren, müssen Sie festlegen `TDF_SHOW_PROGRESS_BAR` erwartet haben.  
  
 `TDF_CALLBACK_TIMER`  
 Gibt an, dass die `CTaskDialog` Rückruf Intervall auf ca. 200 Millisekunden festgelegt.  
  
 `TDF_POSITION_RELATIVE_TO_WINDOW`  
 Konfiguriert die `CTaskDialog` relativ zum übergeordneten Fensters zentriert werden soll. Wenn dieses Flag nicht aktiviert ist, der `CTaskDialog` ist relativ zu dem Monitor zentriert.  
  
 `TDF_RTL_LAYOUT`  
 Konfiguriert die `CTaskDialog` für ein rechts-nach-links-lesen-Layout.  
  
 `TDF_NO_DEFAULT_RADIO_BUTTON`  
 Gibt an, dass keine Option ausgewählt ist bei der `CTaskDialog` wird angezeigt.  
  
 `TDF_CAN_BE_MINIMIZED`  
 Ermöglicht es dem Benutzer zur Minimierung der `CTaskDialog`. Diese Option unterstützt die `CTaskDialog` kann nicht gebunden werden. MFC unterstützt diese Option nicht, da MFC ein ohne Modus nicht unterstützt `CTaskDialog`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-namesetprogressbarmarqueea--ctaskdialogsetprogressbarmarquee"></a><a name="setprogressbarmarquee"></a>CTaskDialog::SetProgressBarMarquee  
 Konfiguriert eine Marquee-Leiste für die `CTaskDialog` und das Dialogfeld hinzugefügt.  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnabled`  
 `TRUE`So aktivieren Sie die Marquee-Leiste; `FALSE` zum Deaktivieren der Marquee-Leiste, und entfernen Sie sie aus der `CTaskDialog`.  
  
 [in] `nMarqueeSpeed`  
 Eine ganze Zahl, die die Geschwindigkeit der Marquee-Leiste angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Marquee-Leiste angezeigt wird, unter den Haupttext der `CTaskDialog Class`.  
  
 Verwendung `nMarqueeSpeed` , legen Sie die Geschwindigkeit der Marquee-Leiste, größere Werte zeigen eine langsamere Geschwindigkeit. Der Wert 0 für `nMarqueeSpeed` macht die Marquee-Leiste mit der Standard-Geschwindigkeit für verschieben [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro Wenn `nMarqueeSpeed` ist kleiner als 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&4;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="a-namesetprogressbarpositiona--ctaskdialogsetprogressbarposition"></a><a name="setprogressbarposition"></a>CTaskDialog::SetProgressBarPosition  
 Passt die Position der Statusanzeige.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nProgressPos`  
 Die Position für die Statusanzeige zu bewegen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro Wenn `nProgressPos` ist nicht im Bereich Status angezeigt. Sie können ändern, der Fortschritt der Bildlaufleisten-Bereich mit [CTaskDialog::SetProgressBarRange](#setprogressbarrange).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&4;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="a-namesetprogressbarrangea--ctaskdialogsetprogressbarrange"></a><a name="setprogressbarrange"></a>CTaskDialog::SetProgressBarRange  
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
 Die obere Grenze für die Statusanzeige zu bewegen.  
  
### <a name="remarks"></a>Hinweise  
 Die Position der Statusanzeige ist relativ zum `nRangeMin` und `nRangeMax`. Zum Beispiel wenn `nRangeMin` 50 und `nRangeMax` ist 100, eine Position von 75 ist über die Statusanzeige in der Mitte. Verwendung [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) die Position der Statusanzeige fest.  
  
 Zum Anzeigen der Statusleiste die Option `TDF_SHOW_PROGRESS_BAR` muss aktiviert sein und `TDF_SHOW_MARQUEE_PROGRESS_BAR` muss nicht aktiviert werden. Diese Methode legt automatisch `TDF_SHOW_PROGRESS_BAR` und löscht `TDF_SHOW_MARQUEE_PROGRESS_BAR`. Verwendung [CTaskDialog::SetOptions](#setoptions) so ändern Sie die Optionen für diese Instanz manuell die [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md).  
  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro Wenn `nRangeMin` ist nicht kleiner als `nRangeMax`. Diese Methode löst auch eine Ausnahme aus, wenn der `CTaskDialog` wird bereits angezeigt und verfügt über eine Marquee-Statusanzeige.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&4;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="a-namesetprogressbarstatea--ctaskdialogsetprogressbarstate"></a><a name="setprogressbarstate"></a>CTaskDialog::SetProgressBarState  
 Legt den Zustand der Statusanzeige fest und zeigt sie auf der `CTaskDialog`.  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nState`  
 Der Status der Statusanzeige. Finden Sie im Abschnitt "Hinweise" für die möglichen Werte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro Wenn der `CTaskDialog` wird bereits angezeigt und verfügt über eine Marquee-Statusanzeige.  
  
 Die folgende Tabelle enthält die möglichen Werte für `nState`. In all diesen Fällen wird die Statusanzeige mit regulären füllen, bis der festgelegten Tabulatorposition erreicht. An diesem Punkt wird basierend auf den Status geändert.  
  
 PBST_NORMAL  
 Nach der Bearbeitung Anzeige gefüllt, die `CTaskDialog` ändert sich nicht auf die Farbe des Balkens. Standardmäßig ist die reguläre Farbe Grün.  
  
 PBST_ERROR  
 Nach der Bearbeitung Anzeige gefüllt, die `CTaskDialog` ändert sich die Farbe des Balkens, die Farbe. Standardmäßig ist dies Rot.  
  
 PBST_PAUSED  
 Nach der Bearbeitung Anzeige gefüllt, die `CTaskDialog` ändert sich die Farbe des Balkens der angehaltenen Farbe. Standardmäßig ist dies gelb.  
  
 Sie können festlegen, dass die Statusanzeige mit nicht [CTaskDialog::SetProgressBarPosition](#setprogressbarposition).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&4;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="a-namesetradiobuttonoptionsa--ctaskdialogsetradiobuttonoptions"></a><a name="setradiobuttonoptions"></a>CTaskDialog::SetRadioButtonOptions  
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
 `TRUE`So aktivieren Sie das Optionsfeld; `FALSE` auf das Optionsfeld deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro Wenn `nRadioButtonID` ist keine gültige ID für ein Optionsfeld.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&3;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="a-namesetverificationcheckboxa--ctaskdialogsetverificationcheckbox"></a><a name="setverificationcheckbox"></a>CTaskDialog::SetVerificationCheckbox  
 Legt den Aktivierungszustand des Kontrollkästchens Überprüfung fest.  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bChecked`  
 `TRUE`Damit die Überprüfung das Kontrollkästchen aktiviert, wenn die `CTaskDialog` wird angezeigt. `FALSE` haben die Überprüfung das Kontrollkästchen deaktiviert, wenn die `CTaskDialog` wird angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&5;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="a-namesetverificationcheckboxtexta--ctaskdialogsetverificationcheckboxtext"></a><a name="setverificationcheckboxtext"></a>CTaskDialog::SetVerificationCheckboxText  
 Legt den Text fest, der die rechts neben das Kontrollkästchen "Bestätigung" angezeigt wird.  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strVerificationText`  
 Der Text, den neben dem Kontrollkästchen Überprüfung dieser Methode angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine Ausnahme mit der [sicherstellen, dass](http://msdn.microsoft.com/library/738c4ccf-c29c-4c04-8d6c-f126bedf6e91) Makro, wenn diese Instanz von der `CTaskDialog Class` wird bereits angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&5;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="a-namesetwindowtitlea--ctaskdialogsetwindowtitle"></a><a name="setwindowtitle"></a>CTaskDialog::SetWindowTitle  
 Legt den Titel der `CTaskDialog`.  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strWindowTitle`  
 Den neuen Titel für die `CTaskDialog`.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#7;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="a-nameshowdialoga--ctaskdialogshowdialog"></a><a name="showdialog"></a>CTaskDialog::ShowDialog  
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
 Die Zeichenfolge, für den Inhalt der `CTaskDialog`.  
  
 [in] `strMainInstruction`  
 Die Anweisung von der `CTaskDialog`.  
  
 [in] `strTitle`  
 Der Titel der `CTaskDialog`.  
  
 [in] `nIDCommandControlsFirst`  
 Die Zeichenfolgen-ID des ersten Befehls.  
  
 [in] `nIDCommandControlsLast`  
 Die Zeichenfolgen-ID des letzten Befehls.  
  
 [in] `nCommonButtons`  
 Eine Maske der Schaltflächen zum Hinzufügen der `CTaskDialog`.  
  
 [in] `nTaskDialogOptions`  
 Der Satz von Optionen für die `CTaskDialog`.  
  
 [in] `strFooter`  
 Die Zeichenfolge, die als Fußzeile verwenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die die vom Benutzer vorgenommene Auswahl entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Diese statische Methode ermöglicht Ihnen die Erstellung eine Instanz von der `CTaskDialog Class` ohne explizite Erstellung einer `CTaskDialog` Objekts in Ihrem Code. Da gibt es keine `CTaskDialog` -Objekt können nicht Sie andere Methoden der der `CTaskDialog` Wenn Sie diese Methode verwenden, um anzuzeigen einen `CTaskDialog` für den Benutzer.  
  
 Diese Methode erstellt die Befehlsschaltfläche-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Tabelle in der Ressourcendatei hat mehrere Zeichenfolgen mit zugeordneten Zeichenfolgen-IDs. Diese Methode fügt ein Befehlsschaltflächen-Steuerelement für jeden gültigen Eintrag in der Zeichenfolgentabelle zwischen `nIDCommandControlsFirst` und `nCommandControlsLast`, inklusive. Für diese Befehlsschaltfläche-Steuerelemente die Zeichenfolge in der Tabelle ist die Beschriftung des Steuerelements und die Zeichenfolgen-ID des Steuerelements.  
  
 Finden Sie unter [CTaskDialog::SetOptions](#setoptions) eine Liste der gültigen Optionen.  
  
 Die `CTaskDialog` wird geschlossen, wenn der Benutzer eine allgemeine Schaltfläche, ein Link-Steuerelement wählt, oder schließt das `CTaskDialog`. Der Rückgabewert ist der Bezeichner, der angibt, wie der Benutzer das Dialogfeld geschlossen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTaskDialog&#1;](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="a-nametaskdialogcallbacka--ctaskdialogtaskdialogcallback"></a><a name="taskdialogcallback"></a>CTaskDialog::TaskDialogCallback  
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
 Der Notification-Code, der die generierte Nachricht angibt.  
  
 [in] `wParam`  
 Weitere Informationen über die Nachricht.  
  
 [in] `lParam`  
 Weitere Informationen über die Nachricht.  
  
 [in] `dwRefData`  
 Ein Zeiger auf die `CTaskDialog` -Objekt, das die Rückrufnachricht gilt.  
  
### <a name="return-value"></a>Rückgabewert  
 Hängt von der jeweiligen Benachrichtigungscode. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des `TaskDialogCallback` die bestimmte Nachricht verarbeitet, und ruft Sie die entsprechende Methode der der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md). Z. B. als Reaktion auf die `TDN_BUTTON_CLICKED` Nachricht `TaskDialogCallback` Aufrufe [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).  
  
 Die Werte für `wParam` und `lParam` hängen von der bestimmten generierte Nachricht. Es ist möglich, dass eine oder beide dieser Werte leer sein. Die folgende Tabelle enthält die Standard-Benachrichtigungen, die unterstützt werden und wie die Werte der `wParam` und `lParam` darstellen. Wenn Sie diese Methode in einer abgeleiteten Klasse überschreiben, sollten Sie den Rückrufcode für jede Nachricht in der folgenden Tabelle implementieren.  
  
|Benachrichtigung|`wParam`-Wert|`lParam`-Wert|  
|--------------------------|--------------------|--------------------|  
|`TDN_CREATED`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_NAVIGATED`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_BUTTON_CLICKED`|Die Befehlsschaltfläche Kontroll-ID usw.|Nicht verwendet.|  
|`TDN_HYPERLINK_CLICKED`|Nicht verwendet.|Ein [LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751) -Struktur, die den Link enthält.|  
|`TDN_TIMER`|Zeit in Millisekunden seit dem `CTaskDialog` erstellt wurde oder der Timer zurückgesetzt wurde.|Nicht verwendet.|  
|`TDN_DESTROYED`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_RADIO_BUTTON_CLICKED`|Die Sender-Schaltfläche-ID.|Nicht verwendet.|  
|`TDN_DIALOG_CONSTRUCTED`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_VERIFICATION_CLICKED`|1, wenn das Kontrollkästchen aktiviert ist, 0, wenn er nicht ist.|Nicht verwendet.|  
|`TDN_HELP`|Nicht verwendet.|Nicht verwendet.|  
|`TDN_EXPANDO_BUTTON_CLICKED`|0, wenn die der Erweiterungsbereich reduziert ist; Wert ungleich NULL, wenn die Erweiterung Text angezeigt wird.|Nicht verwendet.|  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Exemplarische Vorgehensweise: Hinzufügen ein CTaskDialog zu einer Anwendung](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)




