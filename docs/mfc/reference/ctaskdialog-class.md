---
title: Klasse "CTaskDialog" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CTaskDialog [MFC], CTaskDialog
- CTaskDialog [MFC], AddCommandControl
- CTaskDialog [MFC], AddRadioButton
- CTaskDialog [MFC], ClickCommandControl
- CTaskDialog [MFC], ClickRadioButton
- CTaskDialog [MFC], DoModal
- CTaskDialog [MFC], GetCommonButtonCount
- CTaskDialog [MFC], GetCommonButtonFlag
- CTaskDialog [MFC], GetCommonButtonId
- CTaskDialog [MFC], GetOptions
- CTaskDialog [MFC], GetSelectedCommandControlID
- CTaskDialog [MFC], GetSelectedRadioButtonID
- CTaskDialog [MFC], GetVerificationCheckboxState
- CTaskDialog [MFC], IsCommandControlEnabled
- CTaskDialog [MFC], IsRadioButtonEnabled
- CTaskDialog [MFC], IsSupported
- CTaskDialog [MFC], LoadCommandControls
- CTaskDialog [MFC], LoadRadioButtons
- CTaskDialog [MFC], NavigateTo
- CTaskDialog [MFC], OnCommandControlClick
- CTaskDialog [MFC], OnCreate
- CTaskDialog [MFC], OnDestroy
- CTaskDialog [MFC], OnExpandButtonClick
- CTaskDialog [MFC], OnHelp
- CTaskDialog [MFC], OnHyperlinkClick
- CTaskDialog [MFC], OnInit
- CTaskDialog [MFC], OnNavigatePage
- CTaskDialog [MFC], OnRadioButtonClick
- CTaskDialog [MFC], OnTimer
- CTaskDialog [MFC], OnVerificationCheckboxClick
- CTaskDialog [MFC], RemoveAllCommandControls
- CTaskDialog [MFC], RemoveAllRadioButtons
- CTaskDialog [MFC], SetCommandControlOptions
- CTaskDialog [MFC], SetCommonButtonOptions
- CTaskDialog [MFC], SetCommonButtons
- CTaskDialog [MFC], SetContent
- CTaskDialog [MFC], SetDefaultCommandControl
- CTaskDialog [MFC], SetDefaultRadioButton
- CTaskDialog [MFC], SetDialogWidth
- CTaskDialog [MFC], SetExpansionArea
- CTaskDialog [MFC], SetFooterIcon
- CTaskDialog [MFC], SetFooterText
- CTaskDialog [MFC], SetMainIcon
- CTaskDialog [MFC], SetMainInstruction
- CTaskDialog [MFC], SetOptions
- CTaskDialog [MFC], SetProgressBarMarquee
- CTaskDialog [MFC], SetProgressBarPosition
- CTaskDialog [MFC], SetProgressBarRange
- CTaskDialog [MFC], SetProgressBarState
- CTaskDialog [MFC], SetRadioButtonOptions
- CTaskDialog [MFC], SetVerificationCheckbox
- CTaskDialog [MFC], SetVerificationCheckboxText
- CTaskDialog [MFC], SetWindowTitle
- CTaskDialog [MFC], ShowDialog
- CTaskDialog [MFC], TaskDialogCallback
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83b56c82248397c3d355fb365ccb630760a4a741
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076047"
---
# <a name="ctaskdialog-class"></a>CTaskDialog Class

Ein Popupdialogfeld, das wie ein Meldungsfeld funktioniert, aber zusätzliche Informationen für den Benutzer anzeigen kann. `CTaskDialog` enthält auch Funktionen zum Erfassen von Informationen des Benutzers.

## <a name="syntax"></a>Syntax

```
class CTaskDialog : public CObject
```

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[CTaskDialog::CTaskDialog](#ctaskdialog)|Erstellt ein `CTaskDialog`-Objekt.|

### <a name="methods"></a>Methoden

|||
|-|-|
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|Fügt einen Befehl Button-Steuerelements, das `CTaskDialog`.|
|[CTaskDialog::AddRadioButton](#addradiobutton)|Fügt ein Optionsfeld, um die `CTaskDialog`.|
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|Ein Befehl Schaltflächen-Steuerelement oder eine allgemeine Schaltfläche klickt programmgesteuert.|
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|Ein Optionsfeld klickt programmgesteuert.|
|[CTaskDialog::DoModal](#domodal)|Zeigt das `CTaskDialog` an.|
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|Ruft die Anzahl der allgemeinen Schaltflächen zur Verfügung.|
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Konvertiert eine standardmäßige Windows-Schaltfläche, um den Schaltflächentyp für das common zugeordneten der `CTaskDialog` Klasse.|
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|Konvertiert eine der häufig verwendeten Schaltfläche zugeordneten der `CTaskDialog` Klasse, um eine standardmäßige Windows-Schaltfläche.|
|[CTaskDialog::GetOptions](#getoptions)|Gibt Flags für die für diese `CTaskDialog`.|
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|Gibt zurück, das Schaltflächen-Steuerelement für ausgewählten Befehl.|
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|Gibt das ausgewählten Optionsfeld zurück.|
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|Ruft den Zustand des Kontrollkästchens Überprüfung ab.|
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|Bestimmt, ob ein Befehl Schaltflächen-Steuerelement oder eine allgemeine Schaltfläche aktiviert ist.|
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|Bestimmt, ob ein Optionsfeld aktiviert ist.|
|[IsSupported](#issupported)|Bestimmt, ob der Computer, die die Anwendung ausgeführt wird, unterstützt die `CTaskDialog`.|
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|Fügt den Befehl Schaltflächen-Steuerelemente mit Daten aus der Tabelle hinzu.|
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|Fügt den Optionsfelder mit Daten aus der Tabelle hinzu.|
|[CTaskDialog::NavigateTo](#navigateto)|Überträgt den Fokus auf ein anderes `CTaskDialog`.|
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|Das Framework ruft diese Methode aus, klickt der Benutzer einen Befehl Schaltflächen-Steuerelement.|
|[CTaskDialog::OnCreate](#oncreate)|Das Framework ruft diese Methode nach dem Erstellen der `CTaskDialog`.|
|[CTaskDialog::OnDestroy](#ondestroy)|Das Framework ruft diese Methode auf, unmittelbar bevor es zerstört die `CTaskDialog`.|
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|Das Framework ruft diese Methode aus, klickt der Benutzer auf die Schaltfläche "Erweiterung".|
|[CTaskDialog::OnHelp](#onhelp)|Das Framework ruft diese Methode auf, wenn der Benutzer Hilfe anfordert.|
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|Das Framework ruft diese Methode auf, wenn der Benutzer auf einen Link klickt.|
|[CTaskDialog::OnInit](#oninit)|Das Framework ruft diese Methode bei der `CTaskDialog` initialisiert wird.|
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|Das Framework ruft diese Methode auf, wenn der Benutzer den Fokus im Hinblick auf die Steuerelemente auf der `CTaskDialog`.|
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|Das Framework ruft diese Methode auf, wenn der Benutzer ein Optionsfeld-Steuerelement auswählt.|
|[CTaskDialog::OnTimer](#ontimer)|Das Framework ruft diese Methode auf, wenn der Timer abläuft.|
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|Das Framework ruft diese Methode aus, klickt der Benutzer das Kontrollkästchen für die Überprüfung.|
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|Entfernt alle Befehlssteuerelemente aus dem `CTaskDialog`.|
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|Entfernt alle Optionsfelder aus der `CTaskDialog`.|
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|Aktualisiert ein Befehl Schaltflächen-Steuerelement in der `CTaskDialog`.|
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|Aktualisiert eine Teilmenge der allgemeinen Schaltflächen aktiviert sein und erfordern die UAC-rechteerweiterung.|
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|Fügt die allgemeine Schaltflächen, die `CTaskDialog`.|
|[CTaskDialog::SetContent](#setcontent)|Aktualisiert den Inhalt der `CTaskDialog`.|
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|Gibt an, das Schaltflächen-Steuerelement von Standard-Befehl.|
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|Gibt an, das Optionsfeld "Standard".|
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|Passt die Breite der `CTaskDialog`.|
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|Aktualisiert den Expansion-Bereich, der die `CTaskDialog`.|
|[CTaskDialog::SetFooterIcon](#setfootericon)|Aktualisiert die Fußzeile Symbol für die `CTaskDialog`.|
|[CTaskDialog::SetFooterText](#setfootertext)|Aktualisiert den Text in der Fußzeile der `CTaskDialog`.|
|[CTaskDialog::SetMainIcon](#setmainicon)|Das Hauptsymbol des aktualisiert die `CTaskDialog`.|
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|Aktualisiert die Anweisungen von der `CTaskDialog`.|
|[CTaskDialog::SetOptions](#setoptions)|Konfiguriert die Optionen für die `CTaskDialog`.|
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|Konfiguriert eine Marquee-Leiste für die `CTaskDialog` und fügt sie im Dialogfeld hinzu.|
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|Passt die Position der Statusanzeige an.|
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|Passt Bereich der Statusanzeige an.|
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|Legt den Zustand der Statusanzeige fest und zeigt sie auf die `CTaskDialog`.|
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|Aktiviert oder deaktiviert ein Optionsfeld.|
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|Legt den aktivierten Zustand des Kontrollkästchens Überprüfung fest.|
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|Legt den Text auf der rechten Seite des Kontrollkästchens Überprüfung fest.|
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|Definiert den Titel des der `CTaskDialog`.|
|[CTaskDialog::ShowDialog](#showdialog)|Erstellt und zeigt eine `CTaskDialog`.|
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|Das Framework ruft diese als Reaktion auf verschiedene Windows-Meldungen.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|`m_aButtons`|Das Array von Befehl Schaltflächen-Steuerelemente für die `CTaskDialog`.|
|`m_aRadioButtons`|Das Array von Optionsfeld-Steuerelementen für die `CTaskDialog`.|
|`m_bVerified`|`TRUE` Gibt an, dass das Kontrollkästchen für die Überprüfung aktiviert ist; `FALSE` gibt an, dass es nicht.|
|`m_footerIcon`|Das Symbol in der Fußzeile der `CTaskDialog`.|
|`m_hWnd`|Ein Handle für das Fenster für die `CTaskDialog`.|
|`m_mainIcon`|Das Hauptsymbol des der `CTaskDialog`.|
|`m_nButtonDisabled`|Eine Maske, die von der allgemeinen Schaltflächen angibt, sind deaktiviert.|
|`m_nButtonElevation`|Eine Maske, die von der allgemeinen Schaltflächen angibt, müssen UAC-rechteerweiterung.|
|`m_nButtonId`|Die ID des ausgewählten Befehls Button-Steuerelements.|
|`m_nCommonButton`|Eine Maske, die die allgemeinen Schaltflächen angibt werden angezeigt, auf die `CTaskDialog`.|
|`m_nDefaultCommandControl`|Die ID der Schaltfläche steuern, die ausgewählt ist, wenn die `CTaskDialog` wird angezeigt.|
|`m_nDefaultRadioButton`|Die ID des Optionsfelds zu steuern, die ausgewählt ist, wenn die `CTaskDialog` wird angezeigt.|
|`m_nFlags`|Eine Maske, die die Optionen für gibt an, die `CTaskDialog`.|
|`m_nProgressPos`|Die aktuelle Position der Statusanzeige.  Dabei muss es sich um einen Wert zwischen `m_nProgressRangeMin` und `m_nProgressRangeMax` handeln.|
|`m_nProgressRangeMax`|Der maximale Wert für die Statusanzeige.|
|`m_nProgressRangeMin`|Der Mindestwert für die Statusanzeige.|
|`m_nProgressState`|Der Zustand der Statusanzeige. Weitere Informationen finden Sie unter [CTaskDialog::SetProgressBarState](#setprogressbarstate).|
|`m_nRadioId`|Die ID des dem ausgewählten Optionsfeld-Steuerelement.|
|`m_nWidth`|Die Breite der `CTaskDialog` in Pixel.|
|`m_strCollapse`|Die Zeichenfolge der `CTaskDialog` rechts neben dem Feld für die Erweiterung wird angezeigt, wenn die erweiterte Informationen ausgeblendet wird.|
|`m_strContent`|Die Inhaltszeichenfolge der `CTaskDialog`.|
|`m_strExpand`|Die Zeichenfolge der `CTaskDialog` rechts neben dem Feld für die Erweiterung wird angezeigt, wenn die erweiterte Informationen angezeigt werden.|
|`m_strFooter`|Die Fußzeile der `CTaskDialog`.|
|`m_strInformation`|Die erweiterten Informationen für die `CTaskDialog`.|
|`m_strMainInstruction`|Anweisungen von der `CTaskDialog`.|
|`m_strTitle`|Der Titel des der `CTaskDialog`.|
|`m_strVerification`|Die Zeichenfolge, die die `CTaskDialog` rechts neben das Kontrollkästchen für die Überprüfung zeigt.|

## <a name="remarks"></a>Hinweise

Die `CTaskDialog` Klasse ersetzt das standardmäßige Windows-Meldungsfeld und verfügt über zusätzliche Funktionen wie z. B. neue Steuerelemente zum Sammeln von Informationen des Benutzers. Diese Klasse ist in der MFC-Bibliothek in Visual Studio 2010 und höher. Die `CTaskDialog` ab Windows Vista verfügbar ist. In früheren Versionen von Windows können nicht angezeigt. die `CTaskDialog` Objekt. Verwendung `CTaskDialog::IsSupported` zur Laufzeit zu bestimmen, ob der aktuelle Benutzer das Aufgabendialogfeld angezeigt werden kann. Das standardmäßige Windows-Meldungsfeld wird weiterhin unterstützt.

Die `CTaskDialog` steht nur beim Erstellen der Anwendung mithilfe der Unicode-Bibliothek.

Die `CTaskDialog` verfügt über zwei verschiedene Konstruktoren. Ein Konstruktor ermöglicht Ihnen die Angabe von zwei Schaltflächen und maximal sechs regulären Schaltflächen-Steuerelemente. Sie können weitere Schaltflächen hinzufügen, nach der Erstellung der `CTaskDialog`. Der zweite Konstruktor keine Befehlsschaltflächen unterstützt, aber Sie können eine unbegrenzte Anzahl von regulären Schaltflächen-Steuerelemente hinzufügen. Weitere Informationen zu Konstruktoren, finden Sie unter [CTaskDialog::CTaskDialog](#ctaskdialog).

Die folgende Abbildung zeigt ein Beispiel für `CTaskDialog` um den Speicherort der einige der Steuerelemente zu veranschaulichen.

![Beispiel für CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "Ctaskdialogsample") "CTaskDialog"-Beispiel

## <a name="requirements"></a>Anforderungen

**Mindestens erforderliches Betriebssystem:** Windows Vista

**Header:** afxtaskdialog.h

##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl

Fügt einen neuen Befehl Button-Steuerelements, das `CTaskDialog`.

```
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Parameter

*nCommandControlID*<br/>
[in] Die ID der Befehl-Steuerelement.

*strCaption*<br/>
[in] Die Zeichenfolge, die die `CTaskDialog` zeigt dem Benutzer an. Verwenden Sie diese Zeichenfolge, um den Zweck des Befehls zu erläutern.

*bAktiviert*<br/>
[in] Ein boolescher Parameter, der angibt, ob die Schaltfläche "neue" aktiviert oder deaktiviert ist.

*bRequiresElevation*<br/>
[in] Ein boolescher Parameter, der angibt, ob ein Befehl erhöhte Rechte erforderlich sind.

### <a name="remarks"></a>Hinweise

Die `CTaskDialog Class` kann eine unbegrenzte Anzahl von Schaltflächen-Befehlssteuerelemente anzeigen. Aber wenn eine `CTaskDialog` zeigt Schaltfläche "Befehl" steuert, es kann maximal sechs Schaltflächen anzeigen. Wenn eine `CTaskDialog` enthält kein Befehl Button-Steuerelemente, es kann eine unbegrenzte Anzahl von Schaltflächen anzeigen.

Bei der Auswahl eine Befehls-Schaltflächen-Steuerelement, das `CTaskDialog` geschlossen wird. Wenn die Anwendung zeigt das Dialogfeld mit [CTaskDialog::DoModal](#domodal), `DoModal` gibt die *nCommandControlID* des ausgewählten Befehls Button-Steuerelements.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="addradiobutton"></a>  CTaskDialog::AddRadioButton

Fügt ein Optionsfeld, um die `CTaskDialog`.

```
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Parameter

*nRadioButtonID*<br/>
[in] Die ID des Optionsfelds.

*strCaption*<br/>
[in] Die Zeichenfolge, die die `CTaskDialog` wird neben das Optionsfeld "angezeigt.

*bAktiviert*<br/>
[in] Ein boolescher Parameter, der angibt, ob das Optionsfeld aktiviert ist.

### <a name="remarks"></a>Hinweise

Die Optionsfelder für die [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) ermöglichen es Ihnen, Informationen vom Benutzer zu erfassen. Verwenden Sie die Funktion [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) um zu bestimmen, welches Optionsfeld ausgewählt ist.

Die `CTaskDialog` nicht erfordert, dass die *nRadioButtonID* Parameter für jedes Optionsfeld eindeutig sind. Sie können jedoch unerwartetes Verhalten auftreten, wenn Sie keinen unterschiedlichen Bezeichner für jedes Optionsfeld verwenden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="clickcommandcontrol"></a>  CTaskDialog::ClickCommandControl

Ein Befehl Schaltflächen-Steuerelement oder eine allgemeine Schaltfläche klickt programmgesteuert.

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>Parameter

*nCommandControlID*<br/>
[in] Die Befehls-ID des Steuerelements klicken.

### <a name="remarks"></a>Hinweise

Diese Methode wird die Windows-Meldung TDM_CLICK_BUTTON generiert.

##  <a name="clickradiobutton"></a>  CTaskDialog::ClickRadioButton

Ein Optionsfeld klickt programmgesteuert.

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>Parameter

*nRadioButtonID*<br/>
[in] Die ID des Optionsfelds auf.

### <a name="remarks"></a>Hinweise

Diese Methode wird die Windows-Meldung TDM_CLICK_RADIO_BUTTON generiert.

##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog

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

*strContent*<br/>
[in] Die Zeichenfolge, die für den Inhalt des verwenden die `CTaskDialog`.

*strMainInstruction*<br/>
[in] Anweisungen von der `CTaskDialog`.

*strTitle*<br/>
[in] Der Titel des der `CTaskDialog`.

*nCommonButtons*<br/>
[in] Eine Maske der allgemeinen Schaltflächen, um das Hinzufügen der `CTaskDialog`.

*nTaskDialogOptions*<br/>
[in] Der Satz von Optionen für die Verwendung der `CTaskDialog`.

*strFooter*<br/>
[in] Die Zeichenfolge, die als die Fußzeile verwendet werden soll.

*nIDCommandControlsFirst*<br/>
[in] Die Zeichenfolgen-ID des ersten Befehls.

*nIDCommandControlsLast*<br/>
[in] Die Zeichenfolgen-ID, der dem letzten Befehl werden soll.

### <a name="remarks"></a>Hinweise

Es gibt zwei Möglichkeiten, die Sie hinzufügen, können ein `CTaskDialog` für Ihre Anwendung. Die erste Möglichkeit ist die Verwendung eines Konstruktors zum Erstellen einer `CTaskDialog` und zeigen Sie sie mithilfe von [CTaskDialog::DoModal](#domodal). Die zweite Möglichkeit ist die Verwendung von der statischen Funktion [CTaskDialog::ShowDialog](#showdialog), können Sie zum Anzeigen einer `CTaskDialog` ohne explizite Erstellung einer `CTaskDialog` Objekt.

Der zweite Konstruktor erstellt die Befehlsschaltfläche-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Tabelle in der Ressourcendatei verfügt über mehrere Zeichenfolgen mit zugeordneten Zeichenfolgen-IDs. Diese Methode fügt ein Befehl Schaltflächen-Steuerelement für jedes gültigen Eintrags in der Zeichenfolgentabelle zwischen *nIDCommandControlsFirst* und *nCommandControlsLast*(inklusiv) enthalten. Für diesen Befehl Schaltflächen-Steuerelemente die Zeichenfolge in der Zeichenfolgentabelle wird die Beschriftung des Steuerelements, und die Zeichenfolgen-ID ist der ID des Steuerelements

Finden Sie unter [CTaskDialog::SetOptions](#setoptions) eine Liste der gültigen Optionen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="domodal"></a>  CTaskDialog::DoModal

Zeigt die `CTaskDialog` und gebunden.

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parameter

*hParent*<br/>
[in] Das übergeordnete Fenster für die `CTaskDialog`.

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, die die vom Benutzer vorgenommene Auswahl entspricht.

### <a name="remarks"></a>Hinweise

Zeigt diese Instanz die ["CTaskDialog"](../../mfc/reference/ctaskdialog-class.md). Klicken Sie dann die Anwendung wartet auf den Benutzer aus, um das Dialogfeld zu schließen.

Die `CTaskDialog` wird geschlossen, wenn der Benutzer eine allgemeine Schaltfläche, ein Link-Steuerelement wählt, oder schließt die `CTaskDialog`. Der Rückgabewert ist der Bezeichner, der angibt, wie der Benutzer das Dialogfeld geschlossen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="getcommonbuttoncount"></a>  CTaskDialog::GetCommonButtonCount

Ruft die Anzahl der allgemeinen Schaltflächen ab.

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der allgemeinen Schaltflächen zur Verfügung.

### <a name="remarks"></a>Hinweise

Die allgemeinen Schaltflächen sind die Standardschaltflächen, die Sie zum Bereitstellen [CTaskDialog::CTaskDialog](#ctaskdialog). Die [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) zeigt die Schaltflächen entlang des unteren Randes des Dialogfelds an.

Die Aufzählungsliste der Schaltflächen wird in CommCtrl.h bereitgestellt.

##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag

Konvertiert eine standardmäßige Windows-Schaltfläche, um den Schaltflächentyp für das common zugeordneten der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md).

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>Parameter

*nButtonId*<br/>
[in] Der standardmäßige Windows-Schaltfläche-Wert.

### <a name="return-value"></a>Rückgabewert

Der Wert des entsprechenden `CTaskDialog` allgemeine Schaltfläche. Wenn keine entsprechende allgemeine Schaltfläche vorhanden ist, gibt diese Methode 0 zurück.

##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId

Konvertiert eine der häufig verwendeten Schaltfläche zugeordneten der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) zu einer standard-Windows-Schaltfläche.

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>Parameter

*nFlag*<br/>
[in] Der allgemeine Schaltflächentyp zugeordnet der `CTaskDialog` Klasse.

### <a name="return-value"></a>Rückgabewert

Der Wert der entsprechenden standard-Windows-Schaltfläche. Es ist keine entsprechende Windows-Schaltfläche, gibt die Methode 0 zurück.

##  <a name="getoptions"></a>  CTaskDialog::GetOptions

Gibt Flags für die für diese `CTaskDialog`.

```
int GetOptions() const;
```

### <a name="return-value"></a>Rückgabewert

Die Flags für die `CTaskDialog`.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu den verfügbaren Optionen die [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md), finden Sie unter [CTaskDialog::SetOptions](#setoptions).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="getselectedcommandcontrolid"></a>  CTaskDialog::GetSelectedCommandControlID

Gibt zurück, das Schaltflächen-Steuerelement für ausgewählten Befehl.

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>Rückgabewert

Die ID des derzeit ausgewählten Befehl Button-Steuerelements.

### <a name="remarks"></a>Hinweise

Sie müssen nicht mithilfe dieser Methode die ID der Befehlsschaltfläche abzurufen, die der Benutzer ausgewählt. Diese ID wird zurückgegeben, entweder durch [CTaskDialog::DoModal](#domodal) oder [CTaskDialog::ShowDialog](#showdialog).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="getselectedradiobuttonid"></a>  CTaskDialog::GetSelectedRadioButtonID

Gibt das ausgewählten Optionsfeld zurück.

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>Rückgabewert

Die ID des ausgewählten Optionsfelds.

### <a name="remarks"></a>Hinweise

Sie können diese Methode verwenden, nachdem der Benutzer das Dialogfeld zum Abrufen des ausgewählten Optionsfelds schließt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="getverificationcheckboxstate"></a>  CTaskDialog::GetVerificationCheckboxState

Ruft den Zustand des Kontrollkästchens Überprüfung ab.

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn Sie dieses Kontrollkästchen, "false" aktiviert ist ist dies nicht.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="iscommandcontrolenabled"></a>  CTaskDialog::IsCommandControlEnabled

Bestimmt, ob ein Befehl Schaltflächen-Steuerelement oder eine Schaltfläche aktiviert ist.

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>Parameter

*nCommandControlID*<br/>
[in] Die ID des Befehls Schaltflächen-Steuerelement oder eine Schaltfläche zum Testen.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Steuerelement, "false" aktiviert ist ist dies nicht.

### <a name="remarks"></a>Hinweise

Sie können diese Methode verwenden, um zu bestimmen, die Verfügbarkeit der sowohl Befehl Schaltflächen-Steuerelemente sowie die allgemeinen Schaltflächen von der `CTaskDialog` Klasse *.

Wenn *nCommandControlID* ist kein gültiger Bezeichner, entweder eine allgemeine `CTaskDialog` Schaltfläche oder ein Befehl Schaltflächen-Steuerelement, löst diese Methode eine Ausnahme aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled

Bestimmt, ob ein Optionsfeld aktiviert ist.

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>Parameter

*nRadioButtonID*<br/>
[in] Die ID des Optionsfelds, um zu testen.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Optionsfeld, "false" aktiviert ist ist dies nicht.

### <a name="remarks"></a>Hinweise

Wenn *nRadioButtonID* ist kein gültiger Bezeichner für ein Optionsfeld, diese Methode löst eine Ausnahme aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="issupported"></a>  IsSupported

Bestimmt, ob der Computer, die die Anwendung ausgeführt wird, unterstützt die `CTaskDialog`.

```
static BOOL IsSupported();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Computer unterstützt die `CTaskDialog`; "False" andernfalls.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion zur Laufzeit zu bestimmen, wenn der Computer, die Ihre Anwendung ausgeführt wird, unterstützt die `CTaskDialog` Klasse. Wenn der Computer nicht unterstützt. die `CTaskDialog`, sollten Sie eine andere Methode für die Kommunikation von Informationen für den Benutzer bereitstellen. Die Anwendung stürzt ab, wenn versucht wird, verwenden Sie eine `CTaskDialog` auf einem Computer, die nicht unterstützt. die `CTaskDialog` Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls

Fügt den Befehl Schaltflächen-Steuerelemente mit Daten aus der Tabelle hinzu.

```
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>Parameter

*nIDCommandControlsFirst*<br/>
[in] Die Zeichenfolgen-ID des ersten Befehls.

*nIDCommandControlsLast*<br/>
[in] Die Zeichenfolgen-ID, der dem letzten Befehl werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode erstellt den Befehl Schaltflächen-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Tabelle in der Ressourcendatei verfügt über mehrere Zeichenfolgen mit zugeordneten Zeichenfolgen-IDs. Neuen Befehl-Schaltflächen-Steuerelemente, die mit dieser Methode hinzugefügt und verwenden Sie die Zeichenfolge für die Beschriftung des Steuerelements und die Zeichenfolgen-ID für die ID des Steuerelements Bereich von Zeichenfolgen, die ausgewählten erfolgt über *nIDCommandControlsFirst* und *nCommandControlsLast*(inklusiv) enthalten. Wenn Sie ein leerer Eintrag in den Bereich vorhanden ist, ist die Methode kein Befehl Schaltflächen-Steuerelement für diesen Eintrag hinzufügen.

Standardmäßig werden neuen Befehl Schaltflächen-Steuerelemente sind aktiviert und erfordern keine Erhöhung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons

RadioButton-Steuerelementen hinzugefügt mithilfe von Daten aus der Tabelle.

```
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>Parameter

*nIDRadioButtonsFirst*<br/>
[in] Die Zeichenfolgen-ID, der das erste Optionsfeld.

*nIDRadioButtonsLast*<br/>
[in] Die Zeichenfolgen-ID des letzten Optionsfelds.

### <a name="remarks"></a>Hinweise

Diese Methode erstellt die Optionsfelder mit Daten aus der Ressourcendatei der Anwendung. Die Tabelle in der Ressourcendatei verfügt über mehrere Zeichenfolgen mit zugeordneten Zeichenfolgen-IDs. Neue Optionsfelder, die mit dieser Methode hinzugefügt und verwenden Sie die Zeichenfolge für das Optionsfeld-Beschriftung und die Zeichenfolgen-ID für das Optionsfeld-ID. Bereich von Zeichenfolgen, die ausgewählten erfolgt über *nIDRadioButtonsFirst* und *nRadioButtonsLast*(inklusiv) enthalten. Wenn Sie ein leerer Eintrag in den Bereich vorhanden ist, wird die Methode kein Optionsfeld für diesen Eintrag hinzufügen.

Standardmäßig sind neue Optionsfelder aktiviert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="navigateto"></a>  CTaskDialog::NavigateTo

Überträgt den Fokus auf ein anderes `CTaskDialog`.

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>Parameter

*oTaskDialog*<br/>
[in] Die `CTaskDialog` , die den Fokus erhält.

### <a name="remarks"></a>Hinweise

Diese Methode blendet Sie aus der aktuellen `CTaskDialog` Wenn es angezeigt wird, die *oTaskDialog*. Die *oTaskDialog* wird am gleichen Speicherort wie die aktuelle `CTaskDialog`.

##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick

Das Framework ruft diese Methode aus, klickt der Benutzer einen Befehl Schaltflächen-Steuerelement.

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>Parameter

*nCommandControlID*<br/>
[in] Die ID des Befehls Button-Steuerelements, die der Benutzer ausgewählt.

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="oncreate"></a>  CTaskDialog::OnCreate

Das Framework ruft diese Methode nach dem Erstellen der `CTaskDialog`.

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="ondestroy"></a>  CTaskDialog::OnDestroy

Das Framework ruft diese Methode auf, unmittelbar bevor es zerstört die `CTaskDialog`.

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="onexpandbuttonclick"></a>  CTaskDialog::OnExpandButtonClick

Das Framework ruft diese Methode aus, klickt der Benutzer auf die Schaltfläche "Erweiterung".

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>Parameter

*bExpanded*<br/>
[in] Ein Wert ungleich Null gibt an, dass die zusätzliche Informationen angezeigt werden; 0 gibt an, dass die zusätzliche Informationen ausgeblendet ist.

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="onhelp"></a>  CTaskDialog::OnHelp

Das Framework ruft diese Methode auf, wenn der Benutzer Hilfe anfordert.

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="onhyperlinkclick"></a>  CTaskDialog::OnHyperlinkClick

Das Framework ruft diese Methode auf, wenn der Benutzer auf einen Link klickt.

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>Parameter

*strHref*<br/>
[in] Die Zeichenfolge, die den Link darstellt.

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [ShellExecute](/windows/desktop/api/shellapi/nf-shellapi-shellexecutea) vor wird S_OK zurückgegeben.

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="oninit"></a>  CTaskDialog::OnInit

Das Framework ruft diese Methode bei der `CTaskDialog` initialisiert wird.

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="onnavigatepage"></a>  CTaskDialog::OnNavigatePage

Das Framework ruft diese Methode als Reaktion auf die [CTaskDialog::NavigateTo](#navigateto) Methode.

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="onradiobuttonclick"></a>  CTaskDialog::OnRadioButtonClick

Das Framework ruft diese Methode auf, wenn der Benutzer ein Optionsfeld-Steuerelement auswählt.

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>Parameter

*nRadioButtonID*<br/>
[in] Die ID der das Optionsfeld-Steuerelement, das der Benutzer geklickt hat.

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="ontimer"></a>  CTaskDialog::OnTimer

Das Framework ruft diese Methode auf, wenn der Timer abläuft.

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>Parameter

*lTime*<br/>
[in] Zeit in Millisekunden seit dem `CTaskDialog` erstellt wurde oder der Zeitgeber zurückgesetzt wurde.

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="onverificationcheckboxclick"></a>  CTaskDialog::OnVerificationCheckboxClick

Das Framework ruft diese Methode aus, klickt der Benutzer das Kontrollkästchen für die Überprüfung.

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>Parameter

*bChecked*<br/>
[in] TRUE gibt an, dass das Kontrollkästchen für die Überprüfung aktiviert ist; FALSE gibt an, dass es nicht ist.

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="removeallcommandcontrols"></a>  CTaskDialog::RemoveAllCommandControls

Entfernt alle dem Befehl Schaltflächen-Steuerelemente aus der `CTaskDialog`.

```
void RemoveAllCommandControls();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="removeallradiobuttons"></a>  CTaskDialog::RemoveAllRadioButtons

Entfernt alle Optionsfelder aus der `CTaskDialog`.

```
void RemoveAllRadioButtons();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions

Aktualisiert ein Befehl Schaltflächen-Steuerelement in der `CTaskDialog`.

```
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>Parameter

*nCommandControlID*<br/>
[in] Die ID des Steuerelements zu aktualisieren.

*bAktiviert*<br/>
[in] Ein boolescher Parameter, der angibt, ob der angegebene Befehl Schaltflächen-Steuerelement aktiviert oder deaktiviert ist.

*bRequiresElevation*<br/>
[in] Ein boolescher Parameter, der angibt, ob das Schaltflächen-Steuerelement des angegebenen Befehl erhöhte Rechte erforderlich sind.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie ändern, ob ein Befehl Schaltflächen-Steuerelement aktiviert ist, oder erfordert erhöhte Rechte, nachdem er hinzugefügt wurde die `CTaskDialog` Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions

Aktualisiert eine Teilmenge der allgemeinen Schaltflächen aktiviert sein und UAC-rechteerweiterung erforderlich ist.

```
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Parameter

*nDisabledButtonMask*<br/>
[in] Eine Maske für die allgemeinen Schaltflächen zu deaktivieren.

*nElevationButtonMask*<br/>
[in] Eine Maske für die allgemeinen Schaltflächen, die erhöhte Rechte erfordern.

### <a name="remarks"></a>Hinweise

Sie können die allgemeinen Schaltflächen verfügbar festlegen, mit einer Instanz von der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md) mithilfe des Konstruktors [CTaskDialog::CTaskDialog](#ctaskdialog) und die Methode [CTaskDialog::SetCommonButtons ](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` unterstützt keine neue allgemeine Schaltflächen hinzufügen.

Wenn Sie diese Methode verwenden, deaktivieren, oder erhöhen eine allgemeine Schaltfläche, die für diese nicht verfügbar ist `CTaskDialog`, diese Methode löst eine Ausnahme aus, mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro.

Mit dieser Methode können keine der Schaltflächen, die zur Verfügung steht die `CTaskDialog` ist jedoch nicht in der *nDisabledButtonMask*, auch wenn sie zuvor deaktiviert war. Diese Methode behandelt die Erhöhung der Rechte auf ähnliche Weise: Zeichnet allgemeine Schaltflächen keine Erhöhung der Rechte erfordern, ist die Schaltfläche "common" verfügbar, aber nicht Bestandteil *nElevationButtonMask*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

##  <a name="setcommonbuttons"></a>  CTaskDialog::SetCommonButtons

Fügt die allgemeine Schaltflächen, die `CTaskDialog`.

```
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>Parameter

*nButtonMask*<br/>
[in] Eine Maske der Schaltflächen zum Hinzufügen der `CTaskDialog`.

*nDisabledButtonMask*<br/>
[in] Eine Maske der Schaltflächen, um Sie zu deaktivieren.

*nElevationButtonMask*<br/>
[in] Eine Maske der Schaltflächen, die erhöhte Rechte erfordern.

### <a name="remarks"></a>Hinweise

Diese Methode nicht nach dem das Anzeigefenster aufrufen werden, für diese Instanz die `CTaskDialog` -Klasse erstellt wird. Wenn Sie dies tun, löst diese Methode eine Ausnahme aus.

Die Schaltflächen erkennbar *nButtonMask* überschreiben alle allgemeinen Schaltflächen, die zuvor hinzugefügt haben, um die `CTaskDialog`. Nur die Schaltflächen in angegebenen *nButtonMask* stehen zur Verfügung.

Wenn entweder *nDisabledButtonMask* oder *nElevationButtonMask* enthalten eine Schaltfläche, der nicht *nButtonMask*, diese Methode löst eine Ausnahme aus, mit der [Stellen Sie sicher](diagnostic-services.md#ensure) Makro.

Standardmäßig werden alle allgemeine Schaltflächen sind aktiviert und erfordern keine Erhöhung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

##  <a name="setcontent"></a>  CTaskDialog::SetContent

Aktualisiert den Inhalt der `CTaskDialog`.

```
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>Parameter

*strContent*<br/>
[in] Die Zeichenfolge, die für den Benutzer anzuzeigen.

### <a name="remarks"></a>Hinweise

Den Inhalt der `CTaskDialog` -Klasse ist der Text, der für den Benutzer im Abschnitt "main" im Dialogfeld angezeigt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl

Gibt an, das Schaltflächen-Steuerelement von Standard-Befehl.

```
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>Parameter

*nCommandControlID*<br/>
[in] Die ID des Schaltflächen-Steuerelement der Standardprojekt.

### <a name="remarks"></a>Hinweise

Schaltflächen-Steuerelement der Standardwert ist das Steuerelement, das ausgewählt, wenn die `CTaskDialog` zuerst an den Benutzer angezeigt wird.

Diese Methode löst eine Ausnahme aus, wenn das anhand des Befehls Schaltflächen-Steuerelement nicht gefunden *nCommandControlID*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton

Gibt an, das Optionsfeld "Standard".

```
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>Parameter

*nRadioButtonID*<br/>
[in] Die ID des Optionsfelds Standardprojekt.

### <a name="remarks"></a>Hinweise

Das Optionsfeld "Standard" ist die Schaltfläche, die ausgewählt, wenn die `CTaskDialog` zuerst an den Benutzer angezeigt wird.

Diese Methode löst eine Ausnahme aus, wenn es nicht, dass das Optionsfeld gemäß finden *nRadioButtonID*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setdialogwidth"></a>  CTaskDialog::SetDialogWidth

Passt die Breite der `CTaskDialog`.

```
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
[in] Die Breite des Dialogfelds, in Pixel.

### <a name="remarks"></a>Hinweise

Der Parameter *nWidth* muss größer als oder gleich 0 sein. Andernfalls löst diese Methode eine Ausnahme aus.

Wenn *nWidth* auf 0 (null) dieser Methode wird das Dialogfeld auf den Standardwert festgelegt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setexpansionarea"></a>  CTaskDialog::SetExpansionArea

Aktualisiert den Expansion-Bereich, der die `CTaskDialog`.

```
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>Parameter

*strExpandedInformation*<br/>
[in] Die Zeichenfolge, die die `CTaskDialog` im Hauptteil des Dialogfelds angezeigt wird, klickt der Benutzer die Schaltfläche "Erweiterung".

*strCollapsedLabel*<br/>
[in] Die Zeichenfolge, die die `CTaskDialog` neben der Schaltfläche "Expansion" zeigt an, wenn der erweiterte Bereich reduziert wird.

*strExpandedLabel*<br/>
[in] Die Zeichenfolge, die die `CTaskDialog` neben der Schaltfläche "Expansion" zeigt an, wenn der erweiterte Bereich angezeigt wird.

### <a name="remarks"></a>Hinweise

Erweiterungsbereich der `CTaskDialog` -Klasse können Sie zusätzliche Informationen für den Benutzer bereitzustellen. Die Erweiterungsbereich enthält, in den Hauptteil des der `CTaskDialog`befindet sich direkt unter den Titel und Inhalt der Zeichenfolge.

Wenn die `CTaskDialog` wird an erster Stelle angezeigt, es nicht die erweiterte Informationen angezeigt und setzt `strCollapsedLabel` neben der Schaltfläche "Erweiterung". Klickt der Benutzer die Schaltfläche "Erweiterung", die `CTaskDialog` zeigt *StrExpandedInformation* und ändert die Bezeichnung *StrExpandedLabel*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setfootericon"></a>  CTaskDialog::SetFooterIcon

Aktualisiert die Fußzeile-Symbol, der die `CTaskDialog`.

```
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>Parameter

*hFooterIcon*<br/>
[in] Das Symbol "Neu", für die `CTaskDialog`.

*lpszFooterIcon*<br/>
[in] Das Symbol "Neu", für die `CTaskDialog`.

### <a name="remarks"></a>Hinweise

Das Symbol für die Fußzeile wird angezeigt, am unteren Rand der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md). Sie können Fußzeilentext zugeordnet sein. Sie können ändern, den Fußzeilentext mit [CTaskDialog::SetFooterText](#setfootertext).

Diese Methode löst eine Ausnahme mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro Wenn die `CTaskDialog` angezeigt wird oder der Eingabeparameter NULL ist.

Ein `CTaskDialog` lässt nur eine `HICON` oder `LPCWSTR` als eine Fußzeile-Symbol. Dies wird durch Festlegen der Option TDF_USE_HICON_FOOTER im Konstruktor konfiguriert oder [CTaskDialog::SetOptions](#setoptions). In der Standardeinstellung die `CTaskDialog` für die Verwendung konfiguriert `LPCWSTR` als Eingabetyp für die Fußzeile-Symbol. Diese Methode generiert eine Ausnahme aus, wenn Sie versuchen, legen Sie das Symbol mit dem Typ nicht geeignet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setfootertext"></a>  CTaskDialog::SetFooterText

Aktualisiert den Text in der Fußzeile der `CTaskDialog`.

```
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>Parameter

*strFooterText*<br/>
[in] Der neue Text für die Fußzeile.

### <a name="remarks"></a>Hinweise

Das Symbol für die Fußzeile angezeigt wird, neben den Footertext am unteren Rand der `CTaskDialog`. Sie können ändern, dass das Symbol Fußzeile mit [CTaskDialog::SetFooterIcon](#setfootericon).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setmainicon"></a>  CTaskDialog::SetMainIcon

Das Hauptsymbol des aktualisiert die `CTaskDialog`.

```
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>Parameter

*hMainIcon*<br/>
[in] Das Symbol "Neu".

*lpszMainIcon*<br/>
[in] Das Symbol "Neu".

### <a name="remarks"></a>Hinweise

Diese Methode löst eine Ausnahme mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro Wenn die `CTaskDialog` angezeigt wird oder der Eingabeparameter NULL ist.

Ein `CTaskDialog` lässt nur eine `HICON` oder `LPCWSTR` als Haupt-Symbol. Sie können dies durch Festlegen der Option TDF_USE_HICON_MAIN im Konstruktor oder im Konfigurieren der [CTaskDialog::SetOptions](#setoptions) Methode. In der Standardeinstellung die `CTaskDialog` für die Verwendung konfiguriert `LPCWSTR` als Eingabetyp für das Hauptsymbol. Diese Methode generiert eine Ausnahme aus, wenn Sie versuchen, legen Sie das Symbol mit dem Typ nicht geeignet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setmaininstruction"></a>  CTaskDialog::SetMainInstruction

Aktualisiert die Anweisungen von der `CTaskDialog`.

```
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>Parameter

*strInstructions*<br/>
[in] Die neue Haupt-Anweisung.

### <a name="remarks"></a>Hinweise

Anweisungen von der `CTaskDialog` -Klasse ist für den Benutzer in großer Schriftart fett angezeigte Text. Die Datei befindet sich im Dialogfeld unterhalb der Titelleiste angezeigt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setoptions"></a>  CTaskDialog::SetOptions

Konfiguriert die Optionen für die `CTaskDialog`.

```
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>Parameter

*nOptionFlag*<br/>
[in] Der Satz von Flags für die Verwendung der `CTaskDialog`.

### <a name="remarks"></a>Hinweise

Diese Methode löscht die aktuellen Optionen für die `CTaskDialog`. Um die aktuellen Optionen zu erhalten, müssen Sie diese zuerst Abrufen mit [CTaskDialog::GetOptions](#getoptions) und kombinieren Sie diese mit den Optionen, die Sie festlegen möchten.

Die folgende Tabelle enthält alle gültigen Optionen.

|||
|-|-|
|TDF_ENABLE_HYPERLINKS|Ermöglicht die Links in der `CTaskDialog`.|
|TDF_USE_HICON_MAIN|Konfiguriert die `CTaskDialog` verwenden eine `HICON` für das Hauptsymbol. Die Alternative ist die Verwendung einer `LPCWSTR`.|
|TDF_USE_HICON_FOOTER|Konfiguriert die `CTaskDialog` verwenden eine `HICON` für das Symbol für die Fußzeile. Die Alternative ist die Verwendung einer `LPCWSTR`.|
|TDF_ALLOW_DIALOG_CANCELLATION|Ermöglicht dem Benutzer, schließen Sie die `CTaskDialog` mithilfe der Tastatur oder über das Symbol in der Ecke oben rechts im Dialogfeld auch wenn die **Abbrechen** Schaltfläche ist nicht aktiviert. Wenn dieses Flag nicht festgelegt ist und die **Abbrechen** Schaltfläche ist nicht aktiviert, der Benutzer kann nicht das Dialogfeld schließen, mit Alt + F4, die ESC-Taste, oder der Titelleiste die Schaltfläche "Schließen".|
|TDF_USE_COMMAND_LINKS|Konfiguriert die `CTaskDialog` Befehl Schaltflächen-Steuerelemente verwenden.|
|TDF_USE_COMMAND_LINKS_NO_ICON|Konfiguriert die `CTaskDialog` Befehl Schaltflächen-Steuerelemente verwenden, ohne dass ein Symbol neben dem Steuerelement angezeigt. TDF_USE_COMMAND_LINKS überschreibt TDF_USE_COMMAND_LINKS_NO_ICON.|
|TDF_EXPAND_FOOTER_AREA|Gibt an, dass der Erweiterungsbereich derzeit erweitert wird.|
|TDF_EXPANDED_BY_DEFAULT|Bestimmt, ob die Erweiterungsbereich standardmäßig erweitert wird.|
|TDF_VERIFICATION_FLAG_CHECKED|Gibt an, dass das Kontrollkästchen für die Überprüfung derzeit ausgewählt ist.|
|TDF_SHOW_PROGRESS_BAR|Konfiguriert die `CTaskDialog` eine Statusanzeige angezeigt.|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|Konfiguriert die Statusanzeige, um eine Marquee-Statusanzeige angezeigt werden. Wenn Sie diese Option aktivieren, müssen Sie TDF_SHOW_PROGRESS_BAR, damit das erwartete Verhalten festlegen.|
|TDF_CALLBACK_TIMER|Gibt an, dass die `CTaskDialog` Rückruf Intervall auf ca. 200 Millisekunden festgelegt ist.|
|TDF_POSITION_RELATIVE_TO_WINDOW|Konfiguriert die `CTaskDialog` relativ zum übergeordneten Fenster zentriert werden soll. Wenn dieses Flag nicht aktiviert ist, die `CTaskDialog` relativ zu dem Monitor zentriert ist.|
|TDF_RTL_LAYOUT|Konfiguriert die `CTaskDialog` für ein Lesen der rechts-nach-links-Layout.|
|TDF_NO_DEFAULT_RADIO_BUTTON|Gibt an, dass kein Optionsfeld ausgewählt, wird bei der `CTaskDialog` angezeigt wird.|
|TDF_CAN_BE_MINIMIZED|Ermöglicht dem Benutzer zu minimieren die `CTaskDialog`. Zur Unterstützung dieser Option die `CTaskDialog` darf nicht modal sein. MFC unterstützt diese Option nicht, da MFC ein ohne Modus nicht unterstützt. `CTaskDialog`.|

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setprogressbarmarquee"></a>  CTaskDialog::SetProgressBarMarquee

Konfiguriert eine Marquee-Leiste für die `CTaskDialog` und fügt sie im Dialogfeld hinzu.

```
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>Parameter

*bAktiviert*<br/>
[in] True, um die Marquee-Leiste zu aktivieren. "False" zum Deaktivieren der Marquee-Leiste, und entfernen Sie sie aus der `CTaskDialog`.

*nMarqueeSpeed*<br/>
[in] Eine ganze Zahl, die die Geschwindigkeit der Marquee-Leiste angibt.

### <a name="remarks"></a>Hinweise

Die Marquee-Leiste wird angezeigt, darunter den Haupttext der `CTaskDialog` Klasse.

Verwendung *nMarqueeSpeed* , legen Sie die Geschwindigkeit der Marquee-Leiste; größere Werte zeigen eine langsamere Geschwindigkeit. Der Wert 0 für *nMarqueeSpeed* macht die Marquee-Leiste, die mit der Standard-Geschwindigkeit für Windows zu verschieben.

Diese Methode löst eine Ausnahme mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro Wenn *nMarqueeSpeed* ist kleiner als 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarposition"></a>  CTaskDialog::SetProgressBarPosition

Passt die Position der Statusanzeige an.

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Parameter

*nProgressPos*<br/>
[in] Die Position der Statusanzeige.

### <a name="remarks"></a>Hinweise

Diese Methode löst eine Ausnahme mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro Wenn *nProgressPos* befindet sich nicht im Bereich Balken wird ausgeführt. Sie können den Bereich des Status-Leiste mit ändern [CTaskDialog::SetProgressBarRange](#setprogressbarrange).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarrange"></a>  CTaskDialog::SetProgressBarRange

Passt Bereich der Statusanzeige an.

```
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Parameter

*nRangeMin*<br/>
[in] Die untere Grenze der Statusanzeige.

*nRangeMax*<br/>
[in] Die obere Grenze der Statusanzeige.

### <a name="remarks"></a>Hinweise

Die Position der Statusanzeige ist relativ zum *nRangeMin* und *nRangeMax*. Z. B. wenn *nRangeMin* beträgt 50 und *nRangeMax* ist 100, eine Position von 75 ist über die Statusanzeige in der Mitte. Verwendung [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) die Position der Statusanzeige festlegen.

Um die Statusanzeige anzuzeigen, muss die Option, die TDF_SHOW_PROGRESS_BAR aktiviert werden muss und den TDF_SHOW_MARQUEE_PROGRESS_BAR nicht aktiviert werden. Diese Methode legt TDF_SHOW_PROGRESS_BAR automatisch und löscht TDF_SHOW_MARQUEE_PROGRESS_BAR. Verwendung [CTaskDialog::SetOptions](#setoptions) so ändern Sie die Optionen für diese Instanz manuell die [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md).

Diese Methode löst eine Ausnahme mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro Wenn *nRangeMin* ist nicht kleiner als *nRangeMax*. Diese Methode löst außerdem eine Ausnahme aus, wenn die `CTaskDialog` bereits angezeigt wird, und verfügt über eine Marquee-Statusanzeige.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarstate"></a>  CTaskDialog::SetProgressBarState

Legt den Zustand der Statusanzeige fest und zeigt sie auf die `CTaskDialog`.

```
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>Parameter

*nState*<br/>
[in] Der Zustand der Statusanzeige. Finden Sie im Abschnitt "Hinweise" für die möglichen Werte.

### <a name="remarks"></a>Hinweise

Diese Methode löst eine Ausnahme mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro Wenn die `CTaskDialog` bereits angezeigt wird, und verfügt über eine Marquee-Statusanzeige.

Die folgende Tabelle enthält die möglichen Werte für *nState*. In allen diesen Fällen wird die Statusanzeige mit einer regulären füllen, bis die angegebene Stoppposition erreicht. An diesem Punkt wird diese Farbe basierend auf den Zustand ändern.

|||
|-|-|
|PBST_NORMAL|Nach der Bearbeitung Anzeige gefüllt, die `CTaskDialog` ändert sich nicht auf die Farbe des balkenzeigers. Standardmäßig ist die reguläre Farbe Grün.|
|PBST_ERROR|Nach der Bearbeitung Anzeige gefüllt, die `CTaskDialog` ändert sich die Farbe des Balkens, der die Farbe. Standardmäßig ist dies in der Rot.|
|PBST_PAUSED|Nach der Bearbeitung Anzeige gefüllt, die `CTaskDialog` ändert sich die Farbe des Balkens auf die angehaltene Farbe. Standardmäßig ist dies ein gelb.|

Sie können festlegen, dass die Statusanzeige mit nicht [CTaskDialog::SetProgressBarPosition](#setprogressbarposition).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setradiobuttonoptions"></a>  CTaskDialog::SetRadioButtonOptions

Aktiviert oder deaktiviert ein Optionsfeld.

```
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>Parameter

*nRadioButtonID*<br/>
[in] Die ID der das Optionsfeld-Steuerelement.

*bAktiviert*<br/>
[in] True, um das Optionsfeld zu aktivieren. So deaktivieren Sie das Optionsfeld wird false ZURÜCKGEGEBEN.

### <a name="remarks"></a>Hinweise

Diese Methode löst eine Ausnahme mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro Wenn *nRadioButtonID* ist keine gültige ID für ein Optionsfeld.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox

Legt den aktivierten Zustand des Kontrollkästchens Überprüfung fest.

```
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>Parameter

*bChecked*<br/>
[in] Wert true haben das Kontrollkästchen für die Überprüfung ausgewählt, wenn die `CTaskDialog` wird angezeigt. "False", damit Sie das Kontrollkästchen für die Überprüfung nicht ausgewählt, wenn die `CTaskDialog` wird angezeigt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="setverificationcheckboxtext"></a>  CTaskDialog::SetVerificationCheckboxText

Legt den Text an, der die rechts neben das Kontrollkästchen "Überprüfung" angezeigt wird.

```
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>Parameter

*strVerificationText*<br/>
[in] Der Text, den neben dem Kontrollkästchen für die Überprüfung dieser Methode wird angezeigt.

### <a name="remarks"></a>Hinweise

Diese Methode löst eine Ausnahme mit der [stellen Sie sicher](diagnostic-services.md#ensure) Makro, wenn diese Instanz die `CTaskDialog` Klasse bereits angezeigt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle

Definiert den Titel des der `CTaskDialog`.

```
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>Parameter

*strWindowTitle*<br/>
[in] Den neuen Titel für die `CTaskDialog`.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="showdialog"></a>  CTaskDialog::ShowDialog

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

*strContent*<br/>
[in] Die Zeichenfolge, die für den Inhalt des verwenden die `CTaskDialog`.

*strMainInstruction*<br/>
[in] Anweisungen von der `CTaskDialog`.

*strTitle*<br/>
[in] Der Titel des der `CTaskDialog`.

*nIDCommandControlsFirst*<br/>
[in] Die Zeichenfolgen-ID des ersten Befehls.

*nIDCommandControlsLast*<br/>
[in] Die Zeichenfolgen-ID, der dem letzten Befehl werden soll.

*nCommonButtons*<br/>
[in] Eine Maske der Schaltflächen zum Hinzufügen der `CTaskDialog`.

*nTaskDialogOptions*<br/>
[in] Der Satz von Optionen für die Verwendung der `CTaskDialog`.

*strFooter*<br/>
[in] Die Zeichenfolge, die als die Fußzeile verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, die die vom Benutzer vorgenommene Auswahl entspricht.

### <a name="remarks"></a>Hinweise

Diese statische Methode ermöglicht Ihnen die Erstellung eine Instanz von der `CTaskDialog` Klasse ohne explizite Erstellung einer `CTaskDialog` Objekts in Ihrem Code. Da gibt es keine `CTaskDialog` Objekt, Sie können keine andere Methoden Aufrufen der `CTaskDialog` , wenn Sie diese Methode verwenden, um anzuzeigen einer `CTaskDialog` für den Benutzer.

Diese Methode erstellt den Befehl Schaltflächen-Steuerelemente mit Daten aus der Ressourcendatei der Anwendung. Die Tabelle in der Ressourcendatei verfügt über mehrere Zeichenfolgen mit zugeordneten Zeichenfolgen-IDs. Diese Methode fügt ein Befehl Schaltflächen-Steuerelement für jedes gültigen Eintrags in der Zeichenfolgentabelle zwischen *nIDCommandControlsFirst* und *nCommandControlsLast*(inklusiv) enthalten. Für diesen Befehl Schaltflächen-Steuerelemente die Zeichenfolge in der Zeichenfolgentabelle wird die Beschriftung des Steuerelements, und die Zeichenfolgen-ID ist der ID des Steuerelements

Finden Sie unter [CTaskDialog::SetOptions](#setoptions) eine Liste der gültigen Optionen.

Die `CTaskDialog` wird geschlossen, wenn der Benutzer eine allgemeine Schaltfläche, ein Link-Steuerelement wählt, oder schließt die `CTaskDialog`. Der Rückgabewert ist der Bezeichner, der angibt, wie der Benutzer das Dialogfeld geschlossen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

##  <a name="taskdialogcallback"></a>  CTaskDialog::TaskDialogCallback

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

*HWND*<br/>
[in] Ein Handle für die `m_hWnd` -Struktur für die `CTaskDialog`.

*uNotification*<br/>
[in] Der Benachrichtigungscode, der angibt, die generierte Nachricht.

*wParam-Parameter*<br/>
[in] Weitere Informationen zur Meldung.

*lParam*<br/>
[in] Weitere Informationen zur Meldung.

*dwRefData*<br/>
[in] Ein Zeiger auf die `CTaskDialog` -Objekt, das die Rückrufnachricht gilt.

### <a name="return-value"></a>Rückgabewert

Hängt von der bestimmten Benachrichtigungscode. Weitere Informationen finden Sie im Abschnitt Hinweise.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung des `TaskDialogCallback` die bestimmte Nachricht verarbeitet, und klicken Sie dann auf die Methode ruft die entsprechende der [CTaskDialog-Klasse](../../mfc/reference/ctaskdialog-class.md). Beispielsweise als Reaktion auf die Nachricht TDN_BUTTON_CLICKED `TaskDialogCallback` Aufrufe [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick).

Die Werte für *wParam* und *lParam* richten sich nach den spezifischen generierte Nachricht. Es ist möglich, dass eine oder beide der folgenden Werte leer sein. Die folgende Tabelle enthält die standardbenachrichtigungen, die unterstützt werden und was die Werte der *wParam* und *lParam* darstellen. Wenn Sie diese Methode in einer abgeleiteten Klasse überschreiben, sollten Sie der Rückrufcode für jede Nachricht in der folgenden Tabelle implementieren.

|Benachrichtigungsmeldung|*wParam* Wert|*lParam* Wert|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|Nicht verwendet.|Nicht verwendet.|
|TDN_NAVIGATED|Nicht verwendet.|Nicht verwendet.|
|TDN_BUTTON_CLICKED|Die Schaltfläche "Befehl" Kontroll-ID usw.|Nicht verwendet.|
|TDN_HYPERLINK_CLICKED|Nicht verwendet.|Ein [LPCWSTR](/windows/desktop/WinProg/windows-data-types) -Struktur, die den Link enthält.|
|TDN_TIMER|Zeit in Millisekunden seit dem `CTaskDialog` erstellt wurde oder der Zeitgeber zurückgesetzt wurde.|Nicht verwendet.|
|TDN_DESTROYED|Nicht verwendet.|Nicht verwendet.|
|TDN_RADIO_BUTTON_CLICKED|Die Sender-Schaltfläche-ID.|Nicht verwendet.|
|TDN_DIALOG_CONSTRUCTED|Nicht verwendet.|Nicht verwendet.|
|TDN_VERIFICATION_CLICKED|1, wenn Sie dieses Kontrollkästchen aktiviert ist, 0, wenn er nicht ist.|Nicht verwendet.|
|TDN_HELP|Nicht verwendet.|Nicht verwendet.|
|TDN_EXPANDO_BUTTON_CLICKED|0, wenn die Erweiterungsbereich reduziert ist; ungleich NULL, wenn der Erweiterungstext angezeigt wird.|Nicht verwendet.|

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Exemplarische Vorgehensweise: Hinzufügen eines CTaskDialog zu einer Anwendung](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)
