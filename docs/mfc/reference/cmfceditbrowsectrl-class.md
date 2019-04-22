---
title: CMFCEditBrowseCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
helpviewer_keywords:
- CMFCEditBrowseCtrl [MFC], EnableBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFileBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFolderBrowseButton
- CMFCEditBrowseCtrl [MFC], GetMode
- CMFCEditBrowseCtrl [MFC], OnAfterUpdate
- CMFCEditBrowseCtrl [MFC], OnBrowse
- CMFCEditBrowseCtrl [MFC], OnChangeLayout
- CMFCEditBrowseCtrl [MFC], OnDrawBrowseButton
- CMFCEditBrowseCtrl [MFC], OnIllegalFileName
- CMFCEditBrowseCtrl [MFC], SetBrowseButtonImage
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
ms.openlocfilehash: 0c6fb39e17e22bcac60d50b87f7370c6a9f91db9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58770677"
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl-Klasse

Die `CMFCEditBrowseCtrl` Klasse unterstützt das Bearbeitungssteuerelement durchsuchen, als editierbares Textfeld, das optional eine Schaltfläche zum Durchsuchen enthält. Wenn der Benutzer auf die Schaltfläche zum Durchsuchen klicken, führt das Steuerelement eine benutzerdefinierte Aktion aus oder zeigt ein Standarddialogfeld an, das einen Dateibrowser oder einen Ordnerbrowser enthält.

## <a name="syntax"></a>Syntax

```
class CMFCEditBrowseCtrl : public CEdit
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Standardkonstruktor|
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Aktiviert oder deaktiviert (ausgeblendet) die Schaltfläche zum Durchsuchen.|
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Aktiviert die Schaltfläche zum Durchsuchen und fügt Sie in das Bearbeitungssteuerelement und Durchsuchen *Durchsuchen* Modus.|
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Aktiviert die Schaltfläche zum Durchsuchen und fügt Sie in das Bearbeitungssteuerelement und Durchsuchen *Ordnersuche* Modus.|
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Gibt den aktuellen Durchsuchenmodus zurück.|
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Vom Framework aufgerufen, nachdem das Bearbeitungssteuerelement und Durchsuchen, mit dem Ergebnis einer Aktion "Durchsuchen" aktualisiert wurde.|
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Vom Framework aufgerufen, nachdem der Benutzer die Schaltfläche zum Durchsuchen klickt.|
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Zeichnet das aktuelle Steuerelement zum Bearbeiten durchsuchen.|
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Wird aufgerufen, durch das Framework die Durchsuchen-Schaltfläche gezeichnet werden soll.|
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Vom Framework aufgerufen, wenn Sie ein ungültigen Dateinamen in das Bearbeitungssteuerelement eingegeben wurde.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie um weitergeleitet werden die [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows-Funktionen. Syntax und Weitere Informationen finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Legt ein benutzerdefiniertes Image für die Schaltfläche zum Durchsuchen.|

## <a name="remarks"></a>Hinweise

Verwenden Sie ein Bearbeitungssteuerelement für das Durchsuchen, um eine Datei oder einen Ordner namens auszuwählen. Verwenden Sie optional das Steuerelement, z. B. eine benutzerdefinierte Aktion ausführen, um ein Dialogfeld angezeigt. Können Sie anzeigen oder nicht die Schaltfläche zum Durchsuchen angezeigt, und Sie können eine benutzerdefinierte Bezeichnung oder ein Bild auf die Schaltfläche anwenden.

Die *Durchsuchenmodus* von dem Durchsuchen bearbeiten-Steuerelements bestimmt, ob eine Schaltfläche zum Durchsuchen angezeigt und welche Aktion tritt auf, wenn die Schaltfläche geklickt wird. Weitere Informationen finden Sie unter den [GetMode](#getmode) Methode.

Die `CMFCEditBrowseCtrl` Klasse unterstützt die folgenden Modi.

- **Benutzerdefinierter Modus**

   Eine benutzerdefinierte Aktion wird ausgeführt, wenn der Benutzer die Schaltfläche zum Durchsuchen klickt. Sie können z. B. eine anwendungsspezifische-Dialogfeld angezeigt.

- **Datei-Modus**

   Ein Dialogfeld zur standard-Datei wird angezeigt, wenn der Benutzer die Schaltfläche zum Durchsuchen klickt.

- **Folder-Modus**

   Klickt der Benutzer die Schaltfläche zum Durchsuchen, wird ein Dialogfeld zur Standardordner angezeigt.

## <a name="how-to-specify-an-edit-browse-control"></a>Vorgehensweise: Geben Sie ein Bearbeitungssteuerelement für das Durchsuchen

Führen Sie die folgenden Schritte aus, um ein Bearbeitungssteuerelement durchsuchen, in Ihrer Anwendung zu integrieren:

1. Wenn Sie einen benutzerdefinierte Durchsuchen-Modus implementieren möchten, leiten Sie eine eigene Klasse von der `CMFCEditBrowseCtrl` Klasse und überschreiben Sie dann die [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) Methode. Klicken Sie in der überschriebenen Methode führen Sie eine benutzerdefinierte durchsuchungsaktion, und aktualisieren Sie das Bearbeitungssteuerelement und Durchsuchen, mit dem Ergebnis.

1. Betten Sie entweder die `CMFCEditBrowseCtrl` Objekt oder das Bearbeiten von abgeleiteten durchsuchen-Steuerelement-Objekt in das übergeordnete Fenster-Objekt.

1. Bei Verwendung der **-Klassen-Assistent** um ein Dialogfeld zu erstellen, fügen Sie einem Bearbeitungssteuerelement ( `CEdit`) auf dem Formular des Dialogfelds. Darüber hinaus fügen Sie eine Variable für den Zugriff auf das Steuerelement in der Headerdatei hinzu. Ändern Sie in der Headerdatei, den Typ der Variablen vom `CEdit` zu `CMFCEditBrowseCtrl`. Das Bearbeitungssteuerelement und Durchsuchen, wird automatisch erstellt werden. Wenn Sie nicht verwenden die **-Klassen-Assistent**, Hinzufügen einer `CMFCEditBrowseCtrl` Variablen zu Ihrer Headerdatei, und rufen Sie dann die `Create` Methode.

1. Wenn Sie ein Dialogfeld, das ein Bearbeitungssteuerelement für das Durchsuchen hinzugefügt haben, verwenden Sie die **ClassWizard** Tool, um den Datenaustausch einzurichten.

1. Rufen Sie die [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), oder [EnableBrowseButton](#enablebrowsebutton) Methode legen Sie den Durchsuchenmodus und die Schaltfläche zum Durchsuchen angezeigt. Rufen Sie die [GetMode](#getmode) Methode zum Abrufen der aktuellen Durchsuchen-Modus.

1. Um ein benutzerdefiniertes Image für die Schaltfläche "Durchsuchen" bereitzustellen, rufen die [SetBrowseButtonImage](#setbrowsebuttonimage) Methode oder außer Kraft setzen der [OnDrawBrowseButton](#ondrawbrowsebutton) Methode.

1. Rufen Sie zum Entfernen der Schaltfläche zum Durchsuchen von das Bearbeitungssteuerelement und Durchsuchen der [EnableBrowseButton](#enablebrowsebutton) -Methode mit dem *bAktivieren* Parameter auf "false" festgelegt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zwei Methoden in der `CMFCEditBrowseCtrl` Klasse: `EnableFolderBrowseButton` und `EnableFileBrowseButton`. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** afxeditbrowsectrl.h

##  <a name="enablebrowsebutton"></a>  Cmfceditbrowsectrl:: enablebrowsebutton wurde

Zeigt an, oder zeigt nicht die Schaltfläche zum Durchsuchen auf das aktuelle Steuerelement zum Bearbeiten durchsuchen.

```
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
True, um die Schaltfläche "Durchsuchen" angezeigt. "False" nicht auf die Schaltfläche zum Durchsuchen angezeigt werden. Der Standardwert ist "true".

*szLabel*<br/>
Die Bezeichnung, die auf die Schaltfläche zum Durchsuchen angezeigt wird. Der Standardwert ist " **...** ".

### <a name="remarks"></a>Hinweise

Wenn die *bAktivieren* Parameter TRUE ist, implementieren Sie eine benutzerdefinierte Aktion ausführen, wenn die Schaltfläche zum Durchsuchen geklickt wird. Um eine benutzerdefinierte Aktion zu implementieren, leiten Sie eine Klasse von der `CMFCEditBrowseCtrl` Klasse und überschreiben Sie dann die [OnBrowse](#onbrowse) Methode.

Wenn die *bAktivieren* Parameter TRUE ist, wird die Durchsuchen-Modus des Steuerelements `BrowseMode_Default`ist, andernfalls ist der Durchsuchen-Modus `BrowseMode_None`. Weitere Informationen zu den Durchsuchen-Modus, finden Sie unter den [GetMode](#getmode) Methode.

##  <a name="enablefilebrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFileBrowseButton

Zeigt die Schaltfläche zum Durchsuchen auf das aktuelle Steuerelement zum Bearbeiten durchsuchen und versetzt das Steuerelement in *Durchsuchen* Modus.

```
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>Parameter

*lpszDefExt*<br/>
Gibt die Standard-Dateinamenerweiterung an, die im Dialogfeld zur Dateiauswahl verwendet wird. Der Standardwert ist NULL.

*lpszFilter*<br/>
Gibt die Standardfilterzeichenfolge an, die im Dialogfeld zur Dateiauswahl verwendet wird. Der Standardwert ist NULL.

*dwFlags*<br/>
Dialogfeldflags. Der Standardwert ist eine bitweise Kombination (OR) von OFN_HIDEREADONLY und OFN_OVERWRITEPROMPT.

### <a name="remarks"></a>Hinweise

Wenn das Steuerelement zum Bearbeiten und Durchsuchen sich im Dateidurchsuchungsmodus befindet und der Benutzer auf die Schaltfläche zum Durchsuchen klickt, zeigt das Steuerelement das standardmäßige Dialogfeld zur Dateiauswahl an.

Eine vollständige Liste der verfügbaren Flags finden Sie unter [OPENFILENAME-Struktur](/windows/desktop/api/commdlg/ns-commdlg-tagofna).

##  <a name="enablefolderbrowsebutton"></a>  CMFCEditBrowseCtrl::EnableFolderBrowseButton

Zeigt die Schaltfläche zum Durchsuchen auf das aktuelle Steuerelement zum Bearbeiten durchsuchen und versetzt das Steuerelement in *Ordnersuche* Modus.

```
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Hinweise

Wenn das Bearbeitungssteuerelement und Durchsuchen im Ordner Durchsuchen-Modus und der Benutzer auf die Schaltfläche zum Durchsuchen klickt, zeigt das Steuerelement das standardmäßige Dialogfeld zur Ordnerauswahl an.

##  <a name="getmode"></a>  CMFCEditBrowseCtrl::GetMode

Ruft die Durchsuchen-Modus des aktuellen durchsuchen Edit-Steuerelements ab.

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Rückgabewert

Einer der Enumerationswerte, der angibt, den aktuellen Modus der Bearbeitung durchsuchen Steuerelement. Die Durchsuchen-Modus bestimmt, ob das Framework für die Schaltfläche zum Durchsuchen angezeigt und welche Aktion tritt auf, wenn ein Benutzer diese Schaltfläche klickt.

In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:

|Wert|Beschreibung|
|-----------|-----------------|
|`BrowseMode_Default`|**benutzerdefinierten Modus**. Eine vom Programmierer definierte Aktion wird ausgeführt.|
|`BrowseMode_File`|**Dateimodus**. Dialogfeld für die standard-Datei wird angezeigt.|
|`BrowseMode_Folder`|**Folder-Modus**. Dialogfeld für die Ordner "standard" wird angezeigt.|
|`BrowseMode_None`|Schaltfläche "Durchsuchen" wird nicht angezeigt.|

### <a name="remarks"></a>Hinweise

Standardmäßig eine `CMFCEditBrowseCtrl` Objekt wird initialisiert, um `BrowseMode_None` Modus. Ändern Sie den Durchsuchenmodus mit der [cmfceditbrowsectrl:: enablebrowsebutton wurde](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), und [CMFCEditBrowseCtrl::EnableFolderBrowseButton ](#enablefolderbrowsebutton) Methoden.

##  <a name="onafterupdate"></a>  CMFCEditBrowseCtrl::OnAfterUpdate

Vom Framework aufgerufen, nachdem das Bearbeitungssteuerelement und Durchsuchen, mit dem Ergebnis einer Aktion "Durchsuchen" aktualisiert wurde.

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse eine benutzerdefinierte Aktion implementiert.

##  <a name="onbrowse"></a>  CMFCEditBrowseCtrl::OnBrowse

Vom Framework aufgerufen, nachdem der Benutzer die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements durchsuchen klickt.

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um benutzerdefinierten Code ausführen, wenn der Benutzer die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements durchsuchen klickt. Leiten Sie eine eigene Klasse von der `CMFCEditBrowseCtrl` Klasse, und überschreiben seine `OnBrowse` Methode. Implementieren Sie in dieser Methode eine benutzerdefinierte durchsuchungsaktion, und aktualisieren Sie optional im Textfeld des Bearbeitungssteuerelements durchsuchen. Verwenden Sie in Ihrer Anwendung die [EnableBrowseButton](#enablebrowsebutton) Methode zum Platzieren des Bearbeiten-Suchen-Steuerelements in *benutzerdefinierte Suche* Modus.

##  <a name="onchangelayout"></a>  CMFCEditBrowseCtrl::OnChangeLayout

Zeichnet das aktuelle Steuerelement zum Bearbeiten durchsuchen.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn der Durchsuchenmodus, der dem Durchsuchen bearbeiten-Steuerelements geändert wird. Weitere Informationen finden Sie unter [CMFCEditBrowseCtrl::GetMode](#getmode).

##  <a name="ondrawbrowsebutton"></a>  CMFCEditBrowseCtrl::OnDrawBrowseButton

Wird aufgerufen, durch das Framework, um die Schaltfläche zum Durchsuchen auf das Bearbeitungssteuerelement und durchsuchen zu zeichnen.

```
virtual void OnDrawBrowseButton(
    CDC* pDC,
    CRect rect,
    BOOL bIsButtonPressed,
    BOOL bIsButtonHot);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Ein Zeiger zu einem Gerätekontext.

*Rechteck*<br/>
Das umschließende Rechteck der Schaltfläche "Durchsuchen".

*bIsButtonPressed*<br/>
True, wenn die Schaltfläche gedrückt wird. andernfalls "false".

*bIsButtonHot*<br/>
True, wenn die Schaltfläche markiert wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion in einer abgeleiteten Klasse zum Anpassen der Darstellung der Schaltfläche "Durchsuchen".

##  <a name="setbrowsebuttonimage"></a>  CMFCEditBrowseCtrl::SetBrowseButtonImage

Legt ein benutzerdefiniertes Image auf die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements durchsuchen fest.

```
void SetBrowseButtonImage(
    HICON hIcon,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(UINT uiBmpResId);
```

### <a name="parameters"></a>Parameter

*hIcon*<br/>
Das Handle eines Symbols.

*hBitmap*<br/>
Das Handle einer Bitmap.

*uiBmpResId*<br/>
Die Ressourcen-ID einer Bitmap.

*bAutoDestroy*<br/>
True, um das angegebene Symbol oder eine Bitmap zu löschen, wenn diese Methode beendet wird. andernfalls "false". Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um ein benutzerdefiniertes Image auf die Schaltfläche zum Durchsuchen anzuwenden. Standardmäßig erhält das Framework ein Standardabbilds, wenn das Bearbeitungssteuerelement und Durchsuchen im befindet *Durchsuchen* oder *Ordnersuche* Modus.

##  <a name="onillegalfilename"></a>  CMFCEditBrowseCtrl::OnIllegalFileName

Vom Framework aufgerufen, wenn Sie ein ungültigen Dateinamen in das Bearbeitungssteuerelement eingegeben wurde.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>Parameter

*strFileName*<br/>
Gibt den ungültigen Dateinamen an.

### <a name="return-value"></a>Rückgabewert

Sollte "false" zurückgeben, wenn der Dateiname nicht weiter auf das Dialogfeld "Datei" übergeben werden kann. In diesem Fall den Fokus wieder auf das Steuerelement zum Bearbeiten festgelegt ist, und der Benutzer muss weiterhin bearbeiten. Die Standardimplementierung zeigt ein Meldungsfeld, die darüber informiert, dass Informationen zu den ungültigen Dateinamen an und gibt FALSE zurück. Sie können diese Methode überschreiben, korrigieren Sie den Dateinamen und gibt TRUE zurück, für die weitere Verarbeitung.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
