---
title: Cmsceditbrowsectrl-Klasse
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
ms.openlocfilehash: 31fadc0a960ddfcf216951e1af481983b122ea0f
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821303"
---
# <a name="cmfceditbrowsectrl-class"></a>Cmsceditbrowsectrl-Klasse

Die `CMFCEditBrowseCtrl` -Klasse unterstützt das Edit Browse-Steuerelement, ein bearbeitbares Textfeld, das optional eine Schaltfläche zum Durchsuchen enthält Wenn der Benutzer auf die Schaltfläche zum Durchsuchen klicken, führt das Steuerelement eine benutzerdefinierte Aktion aus oder zeigt ein Standarddialogfeld an, das einen Dateibrowser oder einen Ordnerbrowser enthält.

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
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Aktiviert oder deaktiviert (blendet) die Schaltfläche zum Durchsuchen.|
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Aktiviert die Schaltfläche "Durchsuchen" und versetzt das Bearbeitungs Steuerelement zum Bearbeiten in den *Datei* Suchmodus.|
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Aktiviert die Schaltfläche "Durchsuchen" und versetzt das Bearbeitungs Steuerelement zum Bearbeiten in den *Ordner* Suchmodus.|
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Gibt den aktuellen Browse-Modus zurück.|
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Wird von Framework aufgerufen, nachdem das Edit Browse-Steuerelement mit dem Ergebnis einer Aktion zum Durchsuchen aktualisiert wurde.|
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Wird von Framework aufgerufen, nachdem der Benutzer auf die Schaltfläche zum Durchsuchen geklickt hat.|
|[Cmsceditbrowsectrl:: onchangelayout](#onchangelayout)|Zeichnet das aktuelle Edit Browse-Steuerelement neu.|
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Wird von Framework aufgerufen, um die Schaltfläche zum Durchsuchen zu zeichnen.|
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Wird von Framework aufgerufen, wenn ein unzulässiger Dateiname in das Bearbeitungs Steuerelement eingegeben wurde.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Übersetzt Fenster Meldungen, bevor diese an die Windows-Funktionen [translatemess](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) gesendet werden. Syntax und weitere Informationen finden Sie unter [CWnd::P retranslatemess Age](../../mfc/reference/cwnd-class.md#pretranslatemessage).|
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Legt ein benutzerdefiniertes Bild für die Schaltfläche Durchsuchen fest.|

## <a name="remarks"></a>Hinweise

Verwenden Sie ein Edit Browse-Steuerelement, um einen Datei-oder Ordnernamen auszuwählen. Optional können Sie mit dem-Steuerelement eine benutzerdefinierte Aktion ausführen, z. b., um ein Dialogfeld anzuzeigen. Sie können die Schaltfläche zum Durchsuchen anzeigen oder nicht anzeigen, und Sie können eine benutzerdefinierte Bezeichnung oder ein Bild auf die Schaltfläche anwenden.

Der Durchsuchenmodus des Edit Browse-Steuer Elements bestimmt, ob es eine Schaltfläche zum Durchsuchen anzeigt und welche Aktion beim Klicken auf die Schaltfläche auftritt. Weitere Informationen finden Sie unter der [getMode](#getmode) -Methode.

Die `CMFCEditBrowseCtrl` -Klasse unterstützt die folgenden Modi.

- **benutzerdefinierter Modus**

   Eine benutzerdefinierte Aktion wird ausgeführt, wenn der Benutzer auf die Schaltfläche Durchsuchen klickt. Beispielsweise können Sie ein anwendungsspezifisches Dialogfeld anzeigen.

- **Dateimodus**

   Ein Standard Dialogfeld für die Dateiauswahl wird angezeigt, wenn der Benutzer auf die Schaltfläche Durchsuchen klickt.

- **Ordner Modus**

   Wenn der Benutzer auf die Schaltfläche Durchsuchen klickt, wird ein Dialogfeld Standardordner Auswahl angezeigt.

## <a name="how-to-specify-an-edit-browse-control"></a>Vorgehensweise: Edit Browse-Steuerelement angeben

Führen Sie die folgenden Schritte aus, um ein Edit Browse-Steuerelement in Ihrer Anwendung zu integrieren:

1. Wenn Sie einen benutzerdefinierten browseinmodus implementieren möchten, leiten Sie eine eigene Klasse `CMFCEditBrowseCtrl` von der-Klasse ab, und überschreiben Sie dann die [cmfceditbrowsectrl:: onbrowse](#onbrowse) -Methode. Führen Sie in der überschriebenen Methode eine benutzerdefinierte Browse-Aktion aus, und aktualisieren Sie das Edit Browse-Steuerelement mit dem Ergebnis.

1. Betten Sie entweder `CMFCEditBrowseCtrl` das-Objekt oder das abgeleitete Edit Browse-Steuerelement Objekt in das übergeordnete Fenster Objekt ein.

1. Wenn Sie den **Klassen-Assistenten** verwenden, um ein Dialogfeld zu erstellen, fügen Sie `CEdit`dem Dialogfeld Formular ein Bearbeitungs Steuerelement () hinzu. Fügen Sie außerdem eine Variable hinzu, um auf das Steuerelement in der Header Datei zuzugreifen. Ändern Sie in der Header Datei den Typ der Variablen von `CEdit` in. `CMFCEditBrowseCtrl` Das Edit Browse-Steuerelement wird automatisch erstellt. Wenn Sie den **Klassen-Assistenten**nicht verwenden, fügen Sie `CMFCEditBrowseCtrl` der Header Datei eine Variable hinzu, und wenden `Create` Sie dann die zugehörige-Methode an.

1. Wenn Sie ein Edit Browse-Steuerelement zu einem Dialogfeld hinzufügen, verwenden Sie das **ClassWizard** -Tool, um den Datenaustausch einzurichten.

1. Rufen Sie die [enablefolderbrowsebutton](#enablefolderbrowsebutton)-, [enablefilebrowsebutton](#enablefilebrowsebutton)-oder [enablebrowsebutton](#enablebrowsebutton) -Methode auf, um den Durchsuchenmodus festzulegen und die Schaltfläche zum Durchsuchen anzuzeigen. Rufen Sie die [getMode](#getmode) -Methode auf, um den aktuellen Suchmodus zu erhalten.

1. Zum Bereitstellen eines benutzerdefinierten Bilds für die Schaltfläche Durchsuchen rufen Sie die [setbrowsebuttonimage](#setbrowsebuttonimage) -Methode auf, oder überschreiben Sie die [ondrawbrowsebutton](#ondrawbrowsebutton) -Methode

1. Um die Schaltfläche Durchsuchen aus dem Edit Browse-Steuerelement zu entfernen, rufen Sie die Methode [enablebrowsebutton](#enablebrowsebutton) auf, wobei der *benable* -Parameter auf false festgelegt ist

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie zwei Methoden in der `CMFCEditBrowseCtrl` -Klasse `EnableFolderBrowseButton` verwendet `EnableFileBrowseButton`werden: und. Dieses Beispiel ist Teil des Beispiels " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** afxeditbrowsectrl. h

##  <a name="enablebrowsebutton"></a>Cmfceditbrowsectrl:: enablebrowsebutton

Zeigt die Schaltfläche zum Durchsuchen auf dem aktuellen Edit Browse-Steuerelement an oder zeigt Sie nicht an.

```
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
TRUE, um die Schaltfläche zum Durchsuchen anzuzeigen. FALSE: die Schaltfläche zum Durchsuchen wird nicht angezeigt. Der Standardwert ist "true".

*szLabel*<br/>
Die Bezeichnung, die auf der Schaltfläche "Durchsuchen" angezeigt wird. Der Standardwert ist " **...** ".

### <a name="remarks"></a>Hinweise

Wenn der *benable* -Parameter true ist, implementieren Sie eine benutzerdefinierte Aktion, die beim Klicken auf die Schaltfläche Durchsuchen ausgeführt werden soll. Um eine benutzerdefinierte Aktion zu implementieren, leiten Sie eine `CMFCEditBrowseCtrl` Klasse von der-Klasse ab und überschreiben dann die [onbrowse](#onbrowse) -Methode.

Wenn der *benable* -Parameter true ist, ist `BrowseMode_Default`der Durchsuchenmodus des-Steuer Elements, andernfalls ist `BrowseMode_None`der Durchsuchen-Modus. Weitere Informationen zu Browsermodi finden Sie in der [getMode](#getmode) -Methode.

##  <a name="enablefilebrowsebutton"></a>Cmfceditbrowsectrl:: enablefilebrowsebutton

Zeigt die Schaltfläche zum Durchsuchen auf dem aktuellen Edit Browse-Steuerelement an und versetzt das Steuerelement in den *Datei* Suchmodus.

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

Eine vollständige Liste der verfügbaren Flags finden Sie unter [OpenFileName-Struktur](/windows/win32/api/commdlg/ns-commdlg-openfilenamew).

##  <a name="enablefolderbrowsebutton"></a>Cmfceditbrowsectrl:: enablefolderbrowsebutton

Zeigt die Schaltfläche zum Durchsuchen auf dem aktuellen Edit Browse-Steuerelement an und versetzt das Steuerelement in den *Ordner* Suchmodus.

```
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>Hinweise

Wenn sich das Edit Browse-Steuerelement im Ordner Suchmodus befindet und der Benutzer auf die Schaltfläche Durchsuchen klickt, zeigt das Steuerelement das Dialogfeld Standardordner Auswahl an.

##  <a name="getmode"></a>Cmsceditbrowsectrl:: getMode

Ruft den Durchsuchenmodus des aktuellen Edit Browse-Steuer Elements ab.

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Rückgabewert

Einer der Enumerationswerte, der den aktuellen Modus des Edit Browse-Steuer Elements angibt. Der Durchsuchenmodus bestimmt, ob das Framework die Schaltfläche Durchsuchen anzeigt und welche Aktion ausgeführt wird, wenn ein Benutzer auf diese Schaltfläche klickt

In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:

|Wert|Beschreibung|
|-----------|-----------------|
|`BrowseMode_Default`|**benutzerdefinierter Modus**. Eine vom Programmierer definierte Aktion wird ausgeführt.|
|`BrowseMode_File`|**Dateimodus**. Das Dialogfeld Standarddatei Browser wird angezeigt.|
|`BrowseMode_Folder`|**Ordner Modus**. Das Dialogfeld Standardordner Browser wird angezeigt.|
|`BrowseMode_None`|Die Schaltfläche "Durchsuchen" wird nicht angezeigt.|

### <a name="remarks"></a>Hinweise

Standardmäßig wird ein `CMFCEditBrowseCtrl` -Objekt mit dem- `BrowseMode_None` Modus initialisiert. Ändern Sie den Durchsuchenmodus mit den Methoden [cmfceditbrowsectrl:: enablebrowsebutton](#enablebrowsebutton), [cmfceditbrowsectrl:: enablefilebrowsebutton](#enablefilebrowsebutton)und [cmfceditbrowsectrl:: enablefolderbrowsebutton](#enablefolderbrowsebutton) .

##  <a name="onafterupdate"></a>Cmeceditbrowsectrl:: onafterupdate

Wird von Framework aufgerufen, nachdem das Edit Browse-Steuerelement mit dem Ergebnis einer Aktion zum Durchsuchen aktualisiert wurde.

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um eine benutzerdefinierte Aktion zu implementieren.

##  <a name="onbrowse"></a>Cmberceditbrowsectrl:: onbrowse

Wird von Framework aufgerufen, nachdem der Benutzer auf die Schaltfläche zum Durchsuchen geklickt hat.

```
virtual void OnBrowse();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode zum Ausführen von benutzerdefiniertem Code, wenn der Benutzer auf die Schaltfläche zum Durchsuchen des Steuer Elements zum Durchsuchen Leiten Sie eine `OnBrowse` eigene Klasse von `CMFCEditBrowseCtrl` der-Klasse ab, und überschreiben Sie die-Methode Implementieren Sie in dieser Methode eine benutzerdefinierte Aktion zum Durchsuchen, und aktualisieren Sie optional das Textfeld des Steuer Elements "Durchsuchen". Verwenden Sie in Ihrer Anwendung die [enablebrowsebutton](#enablebrowsebutton) -Methode, um das Edit Browse-Steuerelement in den *benutzerdefinierten* Durchsuchenmodus zu versetzen.

##  <a name="onchangelayout"></a>Cmsceditbrowsectrl:: onchangelayout

Zeichnet das aktuelle Edit Browse-Steuerelement neu.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn sich der Durchsuchen-Modus des Edit Browse-Steuer Elements ändert. Weitere Informationen finden Sie unter [cmeceditbrowsectrl:: getMode](#getmode).

##  <a name="ondrawbrowsebutton"></a>Cmfceditbrowsectrl:: ondrawbrowsebutton

Wird von Framework aufgerufen, um die Schaltfläche zum Durchsuchen auf dem Edit Browse-Steuerelement zu zeichnen.

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
Das umgebende Rechteck der Schaltfläche zum Durchsuchen.

*bIsButtonPressed*<br/>
TRUE, wenn die Schaltfläche gedrückt wird. andernfalls false.

*bIsButtonHot*<br/>
TRUE, wenn die Schaltfläche hervorgehoben ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion in einer abgeleiteten Klasse, um die Darstellung der Schaltfläche "Durchsuchen" anzupassen.

##  <a name="setbrowsebuttonimage"></a>Cmeceditbrowsectrl:: setbrowsebuttonimage

Legt ein benutzerdefiniertes Bild auf der Schaltfläche Durchsuchen des Edit-Steuer Elements zum Durchsuchen

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
TRUE, wenn das angegebene Symbol oder die Bitmap gelöscht werden soll, wenn diese Methode beendet wird. andernfalls false. Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um ein benutzerdefiniertes Bild auf die Schaltfläche Durchsuchen anzuwenden. Standardmäßig erhält das Framework ein Standard Abbild, wenn sich das Edit Browse-Steuerelement im *Datei* -oder *Ordner* Suchmodus befindet.

##  <a name="onillegalfilename"></a>CMF-ditbrowsectrl:: onillegalfilename

Wird von Framework aufgerufen, wenn ein unzulässiger Dateiname in das Bearbeitungs Steuerelement eingegeben wurde.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>Parameter

*strFileName*<br/>
Gibt den ungültigen Dateinamen an.

### <a name="return-value"></a>Rückgabewert

Gibt false zurück, wenn der Dateiname nicht weiter an das Datei Dialogfeld weitergegeben werden kann. In diesem Fall wird der Fokus auf das Bearbeitungs Steuerelement zurückgesetzt, und der Benutzer sollte die Bearbeitung fortsetzen. Die Standard Implementierung zeigt ein Meldungs Feld an, das dem Benutzer den ungültigen Dateinamen mitteilt und false zurückgibt. Sie können diese Methode überschreiben, den Dateinamen korrigieren und true zur weiteren Verarbeitung zurückgeben.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
