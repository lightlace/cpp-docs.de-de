---
title: Cmfctoolbardatetimectrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
ms.openlocfilehash: 7ab6a240a403e70446ebc1860474f6cb9e1d71e3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504762"
---
# <a name="cmfctoolbardatetimectrl-class"></a>Cmfctoolbardatetimectrl-Klasse

Eine Symbolleisten-Schaltfläche, die ein Steuerelement für Datums-und Zeitauswahl enthält

## <a name="syntax"></a>Syntax

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Erstellt ein `CMFCToolBarDateTimeCtrl`-Objekt.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer die Schaltfläche während der Anpassung Strecken kann. (Überschreibt [cmfctoolbarbutton:: canbegestreckt](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Kopiert die Eigenschaften einer anderen Symbolleisten Schaltfläche in die aktuelle Schaltfläche. (Überschreibt [cmfctoolbarbutton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Zur künftigen Verwendung reserviert.|
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Kopiert Text von der Symbolleisten-Schaltfläche in ein Menü.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|Ruft das erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung ab, das über die angegebene Befehls-ID verfügt.|
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Gibt einen Zeiger auf das Steuerelement für Datums-und Zeitauswahl zurück.|
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Ruft das Fenster Handle ab, das der Symbolleisten Schaltfläche zugeordnet ist. (Überschreibt [cmfctoolbarbutton:: GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Ruft den ausgewählten Zeitpunkt von einem Steuerelement für die Datums-und Uhrzeit Auswahl ab und legt ihn in einer angegebenen [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur ab.|
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Gibt die ausgewählte Uhrzeit von der Steuerelement Schaltfläche für die Zeitauswahl mit einer angegebenen Befehls-ID zurück.|
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt. (Überschreibt [cmfctoolbarbutton:: havehotborder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche die [WM_COMMAND](/windows/win32/menurc/wm-command) -Nachricht verarbeitet. (Überschreibt [cmfctoolbarbutton:: notifycommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Wird von Framework aufgerufen, wenn die Schaltfläche einem anpassbaren Dialogfeld hinzugefügt wird. (Überschreibt [cmfctoolbarbutton:: onaddto customizepage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Wird von Framework aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den Andock Zustand zu berechnen. (Überschreibt [cmfctoolbarbutton:: oncalculatesize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Wird von Framework aufgerufen, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird. (Überschreibt [cmfctoolbarbutton:: onchangeparser](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Wird von Framework aufgerufen, wenn der Benutzer auf das-Steuerelement klickt. (Überschreibt [cmfctoolbarbutton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste eine WM_CTLCOLOR-Meldung behandelt. (Überschreibt [cmfctoolbarbutton:: onctlcolor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|Wird von Framework aufgerufen, um die Schaltfläche mithilfe der angegebenen Stile und Optionen zu zeichnen. (Überschreibt [cmfctoolbarbutton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Wird von Framework aufgerufen, um die Schaltfläche im **Befehls** Bereich des Dialog Felds **Anpassen** zu zeichnen. (Überschreibt [cmfctoolbarbutton:: ondrawoncustomizelist](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Wird von Framework aufgerufen, wenn sich die globale Schriftart geändert hat. (Überschreibt [cmfctoolbarbutton:: onglobalfontschge](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste verschoben wird. (Überschreibt [cmfctoolbarbutton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Wird von Framework aufgerufen, wenn die Schaltfläche sichtbar oder unsichtbar wird. (Überschreibt [cmfctoolbarbutton:: onShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|Wird von Framework aufgerufen, wenn die Größe oder Position der übergeordneten Symbolleiste geändert wird, und diese Änderung bewirkt, dass die Schaltfläche die Größe ändert. (Überschreibt [cmfctoolbarbutton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste ihren QuickInfo-Text aktualisiert. (Überschreibt [cmfctoolbarbutton:: onupdatetooltip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|Liest dieses Objekt aus einem Archiv oder schreibt es in ein Archiv (überschreibt [cmfctoolbarbutton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)).|
|`CMFCToolBarDateTimeCtrl::SetStyle`|Legt den Stil der Symbolleisten Schaltfläche fest. (Überschreibt [cmfctoolbarbutton:: SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Legt die Uhrzeit und das Datum im Steuerelement für die Zeitauswahl fest.|
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Legt die Uhrzeit und das Datum in allen Instanzen des Steuer Elements für die Zeitauswahl fest, die über eine angegebene Befehls-ID verfügen.|

## <a name="remarks"></a>Hinweise

Ein Beispiel für die Verwendung eines Steuer Elements für die Datums-und Zeitauswahl finden Sie im ToolbarDateTimePicker-Beispiel Projekt. Weitere Informationen zum Hinzufügen von Steuerelement Schaltflächen zu Symbol [leisten finden Sie unter Exemplarische Vorgehensweise: Einfügen von Steuerelementen in](../../mfc/walkthrough-putting-controls-on-toolbars.md)Symbolleisten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbardatetimectrl.h

##  <a name="canbestretched"></a>Cmfctoolbardatetimectrl:: canbegestreckt

Gibt an, ob ein Benutzer die Schaltfläche während der Anpassung Strecken kann.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Standardmäßig ist es dem Benutzer nicht gestattet, eine Symbolleisten-Schaltfläche während der Anpassung zu Strecken. Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: canbegestreckt](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), indem der Benutzer während der Anpassung eine Symbolleisten Schaltfläche für Datum und Uhrzeit Strecken kann.

##  <a name="cmfctoolbardatetimectrl"></a>Cmfctoolbardatetimectrl:: cmfctoolbardatetimectrl

Erstellt und initialisiert ein [cmfctoolbardatetimectrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) -Objekt.

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
in Die Steuerelement-ID.

*iImage*<br/>
in Der Index des Bilds im- `CMFCToolBarImages` Objekt der Symbolleiste.

*dwStyle*<br/>
in Der Stil des `CMFCToolBarDateTimeCtrlImpl` Fensters, das erstellt wird, wenn ein Benutzer auf die Schaltfläche klickt.

*iWidth*<br/>
in Die Breite des Steuer Elements in Pixel.

### <a name="remarks"></a>Hinweise

Dieses Objekt wird mit dem Datum und der Uhrzeit des Systems initialisiert. Der Fenster Stil des internen `CMFCToolBarDateTimeCtrlImpl` Objekts enthält den *dwstyle* -Parameter und die Stile WS_CHILD und WS_VISIBLE. Sie können diese Stile nicht mithilfe `CMFCToolBarDateTimeCtrl::SetStyle`von ändern. Verwenden `SetStyle` Sie, um den Stil `CMFCToolBarDateTimeCtrl` des Steuer Elements zu ändern.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Objekt der `CMFCToolBarDateTimeCtrl` -Klasse erstellt wird. Dieser Code Ausschnitt ist Teil des Beispiels für die [Toolbar-Datums](../../overview/visual-cpp-samples.md)-/Uhrzeitauswahl.

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

##  <a name="copyfrom"></a>Cmfctoolbardatetimectrl:: CopyFrom

Kopiert die Eigenschaften einer anderen Symbolleisten Schaltfläche in die aktuelle Schaltfläche.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
in Ein Verweis auf die Quell Schaltfläche, von der kopiert werden soll.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie eine weitere Symbolleisten Schaltfläche auf diese Symbolleisten Schaltfläche *src* muss den Typ `CMFCToolBarDateTimeCtrl`aufweisen.

##  <a name="exporttomenubutton"></a>Cmfctoolbardatetimectrl:: exporttomendubutton

Kopiert Text von der Symbolleisten-Schaltfläche in ein Menü.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parameter

*menuButton*<br/>
in Ein Verweis auf die Menü Schaltfläche für das Ziel.

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Basisklassen Implementierung ( [cmfctoolbarbutton:: exporttomenubutton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) durch Laden der Zeichen folgen Ressource, die der Befehls-ID des-Steuer Elements zugeordnet ist. Weitere Informationen zu Zeichen folgen Ressourcen finden Sie unter [CStringT:: loadstring](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).

##  <a name="getbycmd"></a>Cmfctoolbardatetimectrl:: getbycmd

Ruft das erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung ab, das über die angegebene Befehls-ID verfügt.

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID der abzurufenden Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Das erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung, das über die angegebene Befehls-ID verfügt, oder `CMFCToolBarDateTimeCtrl` NULL, wenn keine Objekte über die angegebene Befehls-ID verfügen.

### <a name="remarks"></a>Hinweise

Diese Shared Utility-Methode wird von Methoden wie [cmfctoolbardatetimectrl:: settimeall](#settimeall) und [cmfctoolbardatetimectrl:: gettimeall](#gettimeall) verwendet, um das Datum und die Uhrzeit aller Instanzen des Zeitauswahl-Steuer Elements festzulegen oder zu erhalten, die über eine angegebene Befehls-ID verfügen.

##  <a name="getdatetimectrl"></a>Cmfctoolbardatetimectrl:: getdatetimectrl

Gibt einen Zeiger auf das Steuerelement für Datums-und Zeitauswahl zurück.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Steuerelement für Datums-und Zeitauswahl. oder NULL, wenn das Steuerelement nicht vorhanden ist.

### <a name="remarks"></a>Hinweise

Die `CMFCToolBarDateTimeCtrl` -Klasse initialisiert `m_pWndDateTime` den Datenmember, wenn Sie `CMFCToolBarDateTimeCtrl` ein-Objekt in eine Symbolleiste einfügen.

##  <a name="gethwnd"></a>Cmfctoolbardatetimectrl:: GetHwnd

Ruft das Fenster Handle ab, das der Symbolleisten Schaltfläche zugeordnet ist.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Rückgabewert

Das Fenster Handle, das der Symbolleisten Schaltfläche "Datum und Uhrzeit" zugeordnet ist.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die [cmfctoolbarbutton:: GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) -Methode.

##  <a name="gettime"></a>Cmfctoolbardatetimectrl:: getTime

Ruft die ausgewählte Uhrzeit aus dem zugeordneten Steuerelement für Datums-und Zeitauswahl ab und legt Sie in einer angegebenen [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur ab.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Parameter

*timeDest*<br/>
vorgenommen In der ersten Überladung ein [COleDateTime-Klassen](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das die Systemzeit Informationen empfängt. In der zweiten Überladung ein [ctime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Systemzeit Informationen empfängt.

*pTimeDest*<br/>
vorgenommen Ein Zeiger auf die [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur, um die Systemzeit Informationen zu erhalten. Darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

In der ersten Überladung ist der Wert ungleich 0 (null), wenn die Uhrzeit erfolgreich in das [COleDateTime-Klassen](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt geschrieben wurde. andernfalls 0. In der zweiten und dritten Überladung ist der Rückgabewert ein DWORD, das gleich dem dwFlag-Member ist, der in der [nmdatetimechange](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) -Struktur festgelegt wurde.

### <a name="remarks"></a>Hinweise

Die-Methode legt das [nmdatetimechange](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) -Strukturmember-dwFlags fest, um anzugeben, ob die Datums-und Uhrzeit Auswahl auf ein Datum und eine Uhrzeit festgelegt ist. Wenn der Wert GDT_NONE ist, wird das-Steuerelement `no date` auf den Status festgelegt und verwendet den DTS_SHOWNONE-Stil. Wenn der zurückgegebene Wert gleich GDT_VALID ist, wird die Systemzeit erfolgreich am Ziel Speicherort gespeichert.

##  <a name="gettimeall"></a>Cmfctoolbardatetimectrl:: gettimeall

Gibt die Zeit zurück, die vom Benutzer aus der Steuerelement Schaltfläche für die Zeitauswahl mit einer angegebenen Befehls-ID ausgewählt wurde.

```
static BOOL GetTimeAll(
    UINT uiCmd,
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeDest);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Gibt die Befehls-ID einer Symbolleisten Schaltfläche an.

*timeDest*<br/>
vorgenommen In der ersten Überladung ein [COleDateTime-Klassen](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das die Systemzeit Informationen empfängt. In der zweiten Überladung ein [ctime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Systemzeit Informationen empfängt.

*pTimeDest*<br/>
vorgenommen Ein Zeiger auf die [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur, um die Systemzeit Informationen zu erhalten. Darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Wenn das Framework eine Symbolleisten Schaltfläche nicht finden kann, die mit der Befehls-ID *uicmd*übereinstimmt, ist der Rückgabewert in der ersten Überladung NULL, und GDT_NONE in den anderen über Ladungen. Wenn die Symbolleisten Schaltfläche gefunden wird, ist der Rückgabewert mit dem Rückgabewert von einem Aufruf von [cmfctoolbardatetimectrl:: getTime](#gettime) auf dieser Schaltfläche identisch. Der Rückgabewert 0 (null) oder GDT_NONE kann auftreten, wenn die Schaltfläche gefunden wird. Dies deutet `GetTime` darauf hin, dass der-Aufrufwert kein gültiges Datum aus einem anderen Grund zurückgegeben hat.

### <a name="remarks"></a>Hinweise

Diese Methode sucht nach einer Symbolleisten-Schaltfläche, die über die angegebene Befehls-ID verfügt und die [cmfctoolbardatetimectrl:: getTime](#gettime) -Methode auf dieser Schaltfläche aufruft.

##  <a name="havehotborder"></a>Cmfctoolbardatetimectrl:: havehotborder

Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn eine Schaltfläche den Rahmen anzeigt, wenn Sie ausgewählt wird. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode gibt einen Wert ungleich 0 (null) zurück, wenn das Steuerelement sichtbar ist.

##  <a name="notifycommand"></a>Cmfctoolbardatetimectrl:: notifycommand

Gibt an, ob die Schaltfläche die [WM_COMMAND](/windows/win32/menurc/wm-command) -Nachricht verarbeitet.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parameter

*iNotifyCode*<br/>
in Die Benachrichtigungs Meldung, die dem Befehl zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche die WM_COMMAND-Nachricht verarbeitet, oder false, um anzugeben, dass die Nachricht von der übergeordneten Symbolleiste behandelt werden soll.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn es im Begriff ist, eine [WM_COMMAND](/windows/win32/menurc/wm-command) -Nachricht an das übergeordnete Fenster zu senden.

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: notifycommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) durch Verarbeitung der [DTN_DATETIMECHANGE](/windows/win32/Controls/dtn-datetimechange) -Benachrichtigung. Dabei wird der interne Zeit Status aktualisiert und die Time-Eigenschaft aller `CMFCToolBarDateTimeCtrl` Objekte mit derselben Befehls-ID aktualisiert.

##  <a name="onaddtocustomizepage"></a>Cmfctoolbardatetimectrl:: onaddto customizepage

Wird von Framework aufgerufen, wenn die Schaltfläche einem anpassbaren Dialogfeld hinzugefügt wird.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung [cmfctoolbarbutton:: onaddtocustomizepage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)durch Kopieren der Eigenschaften aus dem ersten Date-und Time-Steuerelement in einer beliebigen Symbolleiste, die dieselbe Befehls-ID wie dieses Objekt aufweist. Diese Methode führt keine Aktion aus, wenn keine Symbolleiste über ein Datums-und Uhrzeit Steuerelement verfügt, das dieselbe Befehls-ID wie dieses Objekt aufweist.

Weitere Informationen zum Dialogfeld **Anpassen** finden Sie unter [cmfctoolbarscustomizedialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>Cmfctoolbardatetimectrl:: onchangeparser

Wird von Framework aufgerufen, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Das neue übergeordnete Fenster.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Basisklassen Implementierung ( [cmfctoolbarbutton:: onchangeparser](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), indem das interne `CMFCToolBarDateTimeCtrlImpl` -Objekt neu erstellt wird.

##  <a name="onclick"></a>Cmfctoolbardatetimectrl:: OnClick

Wird von Framework aufgerufen, wenn der Benutzer auf das-Steuerelement klickt.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Genutzt.

*bDelay*<br/>
in Genutzt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Schaltfläche die Klick Nachricht verarbeitet. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Basisklassen Implementierung [cmfctoolbarbutton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), indem Sie einen Wert ungleich 0 (null) zurück `CMFCToolBarDateTimeCtrlImpl` gibt, wenn das interne Objekt sichtbar ist.

##  <a name="onctlcolor"></a>Cmfctoolbardatetimectrl:: onctlcolor

Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste eine WM_CTLCOLOR-Meldung behandelt.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Der Gerätekontext, der die Schaltfläche anzeigt.

*nCtlColor*<br/>
in Genutzt.

### <a name="return-value"></a>Rückgabewert

Ein Handle für den globalen Pinsel, den das Framework zum Zeichnen des Hintergrunds der Schaltfläche verwendet.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Basisklassen Implementierung [cmfctoolbarbutton:: onctlcolor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor), indem die Text-und Hintergrundfarben des bereitgestellten Geräte Kontexts auf die globalen Text-bzw. Hintergrundfarben festgelegt werden.

Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA Structure](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>Cmfctoolbardatetimectrl:: onglobalfontschge

Wird von Framework aufgerufen, wenn sich die globale Schriftart geändert hat.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: onglobalfontschge](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) durch Ändern der Schriftart des Steuer Elements in die der globalen Schriftart.

Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA Structure](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>Cmfctoolbardatetimectrl:: OnMove

Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste verschoben wird.

```
virtual void OnMove();
```

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Standard-Klassen Implementierung ( [cmfctoolbarbutton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)), indem die Position des internen `CMFCToolBarDateTimeCtrlImpl` Objekts aktualisiert wird.

##  <a name="onshow"></a>Cmfctoolbardatetimectrl:: onShow

Wird von Framework aufgerufen, wenn die Schaltfläche sichtbar oder unsichtbar wird.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
in Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter true ist, wird die Schaltfläche angezeigt. Andernfalls ist die Schaltfläche nicht sichtbar.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: onShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) durch Anzeigen der Schaltfläche, wenn *bShow* auf true festgelegt ist. Andernfalls blendet diese Methode die Schaltfläche aus.

##  <a name="onsize"></a>Cmfctoolbardatetimectrl:: OnSize

Wird von Framework aufgerufen, wenn die Größe oder Position der übergeordneten Symbolleiste geändert wird, und diese Änderung bewirkt, dass die Schaltfläche die Größe ändert.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parameter

*iSize*<br/>
in Die neue Breite der Schaltfläche in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Standard-Klassen Implementierung ( [cmfctoolbarbutton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) durch Aktualisieren der Größe und Position des internen `CMFCToolBarDateTimeCtrlImpl` Objekts.

##  <a name="onupdatetooltip"></a>Cmfctoolbardatetimectrl:: onupdatetooltip

Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste ihren QuickInfo-Text aktualisiert.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Das übergeordnete Fenster.

*iButtonIndex*<br/>
in Der null basierte Index der Schaltfläche in der Auflistung der übergeordneten Schaltflächen.

*wndToolTip*<br/>
in Das Steuerelement, das den QuickInfo-Text anzeigt.

*str*<br/>
vorgenommen Ein `CString` -Objekt, das den aktualisierten QuickInfo-Text empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode den QuickInfo-Text aktualisiert. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: onupdatetooltip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), indem der QuickInfo-Text angezeigt wird, der der Schaltfläche zugeordnet ist. Wenn die Schaltfläche nicht horizontal angedockt ist, führt diese Methode keine Aktion aus und gibt false zurück.

##  <a name="settime"></a>Cmfctoolbardatetimectrl:: setTime

Legt die Uhrzeit und das Datum im Steuerelement für die Zeitauswahl fest.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Parameter

*timenew*<br/>
in In der ersten Version ein Verweis auf ein [COleDateTime-Klassen](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das die Uhrzeit enthält, zu der das Steuerelement festgelegt wird. In der zweiten Version ein Zeiger auf ein [ctime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Uhrzeit enthält, zu der das Steuerelement festgelegt wird.

*pTimeNew*<br/>
in Ein Zeiger auf die [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur, die die Uhrzeit enthält, zu der das Steuerelement festgelegt wird.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Legt die Zeit in einem Steuerelement für Datums-und Zeitauswahl durch Aufrufen von [CDateTimeCtrl:: setTime](../../mfc/reference/cdatetimectrl-class.md#settime)fest.

##  <a name="settimeall"></a>Cmfctoolbardatetimectrl:: settimeall

Legt die Uhrzeit und das Datum in allen Instanzen des Steuer Elements für die Zeitauswahl fest, die über eine angegebene Befehls-ID verfügen.

```
static BOOL SetTimeAll(
    UINT uiCmd,
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Gibt die Befehls-ID einer Symbolleisten Schaltfläche an.

*timenew*<br/>
in In der ersten Version ein [COleDateTime-Klassen](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das die Uhrzeit enthält, zu der das Steuerelement festgelegt wird. In der zweiten Version ein Zeiger auf ein [ctime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Uhrzeit enthält, zu der das Steuerelement festgelegt wird.

*pTimeNew*<br/>
in Ein Zeiger auf die [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur, die die Uhrzeit enthält, zu der das Steuerelement festgelegt wird.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sucht eine Symbolleisten-Schaltfläche mit der angegebenen Befehls-ID und legt die Zeit in einem Steuerelement für Datums-und Zeitauswahl fest, indem [cmfctoolbardatetimectrl:: setTime](#settime)aufgerufen wird.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Exemplarische Vorgehensweise: Einfügen von Steuerelementen in eine Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md)
