---
title: CMFCToolBarDateTimeCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4cd4a7c77c5b7a19bff7cf586b55302a9de0cc9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401029"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl-Klasse

Eine Symbolleisten-Schaltfläche, die ein Datums- / Zeitauswahl-Steuerelement enthält.

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
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer während der Anpassung die Schaltfläche gestreckt werden kann. (Überschreibt [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche, auf die Schaltfläche "aktuelle". (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Für zukünftige Verwendung reserviert.|
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Kopiert den Text aus der Symbolleisten-Schaltfläche zu einem Menü.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|Ruft das erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung, die die angegebene Befehls-ID|
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Gibt einen Zeiger auf den Datums- / Zeitauswahl-Steuerelement.|
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Ruft das Fensterhandle, das die Symbolleisten-Schaltfläche zugeordnet ist. (Überschreibt [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Ruft die ausgewählte Zeit aus einem Datums- / Zeitauswahl-Steuerelement ab und setzt es in einem angegebenen [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.|
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Gibt den ausgewählten Zeitraum über die Zeit Zeitauswahl-Steuerelement-Schaltfläche, die eine angegebenen Befehls-ID|
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt. (Überschreibt [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche mit der verarbeitet die [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht. (Überschreibt [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird eine **anpassen** Dialogfeld. (Überschreibt [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnet. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn die Schaltfläche mit der in eine neue Symbolleiste eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer das Steuerelement klickt. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste WM_CTLCOLOR-Meldung verarbeitet. (Überschreibt [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|Wird aufgerufen, durch das Framework zum Zeichnen der Schaltfläche mit der angegebenen Formate und -Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Wird aufgerufen, durch das Framework zum Zeichnen der Schaltfläche der **Befehle** im Bereich der **anpassen** im Dialogfeld. (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Vom Framework aufgerufen, wenn die globale Schriftart geändert hat. (Überschreibt [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird. (Überschreibt [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Vom Framework aufgerufen, wird die Schaltfläche mit der ein- oder ausgeblendet. (Überschreibt [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste die Größe ändert oder Position und diese Änderung führt dazu, dass die Schaltfläche, um die Größe zu ändern. (Überschreibt [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert. (Überschreibt [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|Dieses Objekt aus einem Archiv liest oder schreibt dieses in ein Archiv, (überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|Legt das Format der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Legt das Datum und die in der / Zeitauswahl-Steuerelement fest.|
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Legt das Datum und die in der alle Instanzen der / Zeitauswahl-Steuerelement mit einer angegebenen Befehls-ID.|

## <a name="remarks"></a>Hinweise

Ein Beispiel dafür, wie ein Datums- / Zeitauswahl-Steuerelement verwenden finden Sie das Beispielprojekt ToolbarDateTimePicker. Informationen dazu, wie Sie die Steuerelementschaltflächen in Symbolleisten hinzufügen, finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbardatetimectrl.h

##  <a name="canbestretched"></a>  CMFCToolBarDateTimeCtrl::CanBeStretched

Gibt an, ob ein Benutzer während der Anpassung die Schaltfläche gestreckt werden kann.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Standardmäßig lässt sich das Framework nicht auf den Benutzer eine Symbolleisten-Schaltfläche gestreckt wird, während der Anpassung aus. Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) von dem der Benutzer eine Symbolleisten-Schaltfläche für Datum und Uhrzeit gestreckt wird, während der Anpassung.

##  <a name="cmfctoolbardatetimectrl"></a>  CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl

Erstellt und initialisiert ein [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) Objekt.

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
[in] Die Steuerelement-ID.

*iImage*<br/>
[in] Der Index des Bilds in der Symbolleiste auf die `CMFCToolBarImages` Objekt.

*dwStyle*<br/>
[in] Das Format des der `CMFCToolBarDateTimeCtrlImpl` Fenster, das erstellt wird, wenn ein Benutzer auf die Schaltfläche klickt.

*iWidth*<br/>
[in] Die Breite des Steuerelements in Pixel.

### <a name="remarks"></a>Hinweise

Dieses Objekt wird mit dem Systemdatum und Systemzeit initialisiert. Der Fensterstil des internen `CMFCToolBarDateTimeCtrlImpl` Objekt enthält die *DwStyle* Parameter und die Stile WS_CHILD und WS_VISIBLE. Sie können nicht mit dieser Stile ändern `CMFCToolBarDateTimeCtrl::SetStyle`. Verwendung `SetStyle` so ändern Sie den Stil der der `CMFCToolBarDateTimeCtrl` Steuerelement.

### <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCToolBarDateTimeCtrl` Klasse. Dieser Codeausschnitt ist Teil der [Symbolleiste Datums-/ Zeitauswahl Beispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

##  <a name="copyfrom"></a>  CMFCToolBarDateTimeCtrl::CopyFrom

Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche, auf die Schaltfläche "aktuelle".

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
[in] Ein Verweis auf die Schaltfläche "Quelle", aus dem kopiert werden sollen.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Kopieren von einer anderen Symbolleistenschaltfläche diese Symbolleisten-Schaltfläche auf. *Src* muss vom Typ `CMFCToolBarDateTimeCtrl`.

##  <a name="exporttomenubutton"></a>  CMFCToolBarDateTimeCtrl::ExportToMenuButton

Kopiert den Text aus der Symbolleisten-Schaltfläche zu einem Menü.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parameter

*MenuButton*<br/>
[in] Ein Verweis auf die Menüschaltfläche Ziel.

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) durch Laden der Zeichenfolgenressource, die die Befehls-ID des Steuerelements zugeordnet ist. Weitere Informationen zu Ressourcen Zeichenfolgen sind, finden Sie unter [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).

##  <a name="getbycmd"></a>  CMFCToolBarDateTimeCtrl::GetByCmd

Ruft das erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung, die die angegebene Befehls-ID

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die Befehls-ID der Schaltfläche zum Abrufen.

### <a name="return-value"></a>Rückgabewert

Die erste `CMFCToolBarDateTimeCtrl` Objekt in der Anwendung, die der angegebenen Befehls-ID oder NULL, wenn kein `CMFCToolBarDateTimeCtrl` Objekte verfügen über die angegebene Befehls-ID

### <a name="remarks"></a>Hinweise

Diese gemeinsam genutzte Dienstprogramme-Methode wird von Methoden verwendet, z. B. [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) und [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) festgelegt oder abgerufen, das Datum und die Zeit aller Instanzen Datumsauswahl-Steuerelement, die eine angegebenen Befehls-ID.

##  <a name="getdatetimectrl"></a>  CMFCToolBarDateTimeCtrl::GetDateTimeCtrl

Gibt einen Zeiger auf den Datums- / Zeitauswahl-Steuerelement.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Datums- / Zeitauswahl-Steuerelement; oder NULL, wenn das Steuerelement nicht vorhanden ist.

### <a name="remarks"></a>Hinweise

Die `CMFCToolBarDateTimeCtrl` -Klasse initialisiert den `m_pWndDateTime` Datenmember, die beim Einfügen einer `CMFCToolBarDateTimeCtrl` Objekt in einer Symbolleiste.

##  <a name="gethwnd"></a>  CMFCToolBarDateTimeCtrl::GetHwnd

Ruft das Fensterhandle, das die Symbolleisten-Schaltfläche zugeordnet ist.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Rückgabewert

Das Fensterhandle, das das Datum und Uhrzeit-Symbolleisten-Schaltfläche zugeordnet ist.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) Methode.

##  <a name="gettime"></a>  CMFCToolBarDateTimeCtrl::GetTime

Ruft die ausgewählte Zeit aus das zugeordnete Datum und die / Zeitauswahl-Steuerelement und fügt es in einem angegebenen [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Parameter

*timeDest*<br/>
[out] In der ersten Überladung ist eine [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhält. In der zweiten Überladung ist eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhält.

*pTimeDest*<br/>
[out] Ein Zeiger auf die [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Nicht darf NULL sein.

### <a name="return-value"></a>Rückgabewert

In der ersten Überladung, die ungleich NULL, wenn die Zeit erfolgreich, um geschrieben wurde die [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, andernfalls 0. In der zweiten und dritten-Überladungen, ist der Rückgabewert einen DWORD-Wert, der gleich dem dwFlags-Element, das festgelegt wurde, in der [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) Struktur.

### <a name="remarks"></a>Hinweise

Der Methode wird die [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) -Struktur Member DwFlags, um anzugeben, ob die Datums- / Zeitauswahl auf Datum und Uhrzeit festgelegt ist. Wenn der Wert GDT_NONE, auf das Steuerelement festgelegt `no date` Status und den Stil DTS_SHOWNONE verwendet. Wenn der zurückgegebene Wert GDT_VALID gleich ist, wird die Systemzeit am Zielspeicherort wurde erfolgreich gespeichert.

##  <a name="gettimeall"></a>  CMFCToolBarDateTimeCtrl::GetTimeAll

Gibt die Zeit, die vom Benutzer über die Zeit Zeitauswahl-Steuerelement-Schaltfläche, die eine angegebenen Befehls-ID ausgewählt

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
[in] Gibt an, eine Symbolleisten-Befehlsschaltfläche-ID.

*timeDest*<br/>
[out] In der ersten Überladung ist eine [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhält. In der zweiten Überladung ist eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhält.

*pTimeDest*<br/>
[out] Ein Zeiger auf die [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Nicht darf NULL sein.

### <a name="return-value"></a>Rückgabewert

Wenn das Framework eine Symbolleisten-Schaltfläche nicht finden kann, die die Befehls-ID entspricht *UiCmd*, der Rückgabewert ist 0 (null), in der ersten Überladung und GDT_NONE in alle anderen Überladungen. Wenn die Symbolleisten-Schaltfläche gefunden wird, wird der Rückgabewert ist identisch mit der Rückgabewert von einem Aufruf von [CMFCToolBarDateTimeCtrl::GetTime](#gettime) auf diese Schaltfläche. Ein Rückgabewert Wert 0 (null) oder GDT_NONE kann auftreten, wenn die Schaltfläche mit der gefunden wird, der angibt, dass der Aufruf von `GetTime` hat ein gültiges Datum einem anderen Grund nicht zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode sucht nach einer Symbolleisten-Schaltfläche, die die angegebene Befehls-ID und ruft [CMFCToolBarDateTimeCtrl::GetTime](#gettime) Methode, die auf diese Schaltfläche.

##  <a name="havehotborder"></a>  CMFCToolBarDateTimeCtrl::HaveHotBorder

Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn eine Schaltfläche anzeigt, dessen Rahmen aus, wenn ausgewählt wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode gibt einen Wert ungleich NULL zurück, wenn das Steuerelement sichtbar ist.

##  <a name="notifycommand"></a>  CMFCToolBarDateTimeCtrl::NotifyCommand

Gibt an, ob die Schaltfläche mit der verarbeitet die [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parameter

*iNotifyCode*<br/>
[in] Die Benachrichtigung, die mit dem Befehl zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche mit der verarbeitet die WM_COMMAND-Meldung oder "false" um anzugeben, dass die Nachricht von der übergeordneten Symbolleiste behandelt werden soll.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode aus, wenn es zu senden ist ein [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht für das übergeordnete Fenster.

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) durch die Verarbeitung der [DTN_DATETIMECHANGE](/windows/desktop/Controls/dtn-datetimechange) Benachrichtigung. Aktualisiert den Zeitstatus der internen und aktualisiert die Time-Eigenschaft aller `CMFCToolBarDateTimeCtrl` Objekte mit derselben Befehls-ID

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarDateTimeCtrl::OnAddToCustomizePage

Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird eine **anpassen** Dialogfeld.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), durch Kopieren Sie die Eigenschaften aus das erste Datum und Uhrzeit-Steuerelement in die Symbolleisten, die derselben Befehls-ID wie dieses Objekt hat. Diese Methode bewirkt nichts, wenn keine Symbolleiste ein Steuerelements für Datum und Uhrzeit, das mit derselben Befehls-ID wie dieses Objekt besitzt.

Weitere Informationen zu den **anpassen** im Dialogfeld finden Sie unter [CMFCToolBarsCustomizeDialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>  CMFCToolBarDateTimeCtrl::OnChangeParentWnd

Vom Framework aufgerufen, wenn die Schaltfläche mit der in eine neue Symbolleiste eingefügt wird.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Das neue übergeordnete Fenster.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch Neuerstellen der internen `CMFCToolBarDateTimeCtrlImpl` Objekt.

##  <a name="onclick"></a>  CMFCToolBarDateTimeCtrl::OnClick

Vom Framework aufgerufen, wenn der Benutzer das Steuerelement klickt.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
[in] Nicht verwendet.

*bDelay*<br/>
[in] Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die basisklassenimplementierung [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), durch einen Wert ungleich NULL zurückgeben, wenn die interne `CMFCToolBarDateTimeCtrlImpl` Objekt sichtbar ist.

##  <a name="onctlcolor"></a>  CMFCToolBarDateTimeCtrl::OnCtlColor

Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste WM_CTLCOLOR-Meldung verarbeitet.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Der Gerätekontext, in dem die Schaltfläche angezeigt.

*nCtlColor*<br/>
[in] Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Ein Handle für den globalen Pinsel, den das Framework verwendet, um den Hintergrund der Schaltfläche zu zeichnen.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die basisklassenimplementierung [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)durch Festlegen des Texts und Hintergrundfarben des Gerätekontexts auf den globalen Text bereitgestellten und Hintergrundfarben an, bzw.

Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>  CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged

Vom Framework aufgerufen, wenn die globale Schriftart geändert hat.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) durch Ändern der Schriftart des Steuerelements mit der globalen Schriftart.

Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>  CMFCToolBarDateTimeCtrl::OnMove

Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird.

```
virtual void OnMove();
```

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die standardmäßige Klasse-Implementierung ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) durch Aktualisieren der Position des internen `CMFCToolBarDateTimeCtrlImpl` Objekt.

##  <a name="onshow"></a>  CMFCToolBarDateTimeCtrl::OnShow

Vom Framework aufgerufen, wird die Schaltfläche mit der ein- oder ausgeblendet.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
[in] Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter TRUE ist, ist die Schaltfläche sichtbar. Andernfalls ist die Schaltfläche nicht sichtbar.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) durch Anzeigen der Schaltfläche aus, wenn *bShow* ist "true". Diese Methode ist, andernfalls die Schaltfläche ausgeblendet.

##  <a name="onsize"></a>  CMFCToolBarDateTimeCtrl::OnSize

Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste die Größe ändert oder Position und diese Änderung führt dazu, dass die Schaltfläche, um die Größe zu ändern.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parameter

*iSize*<br/>
[in] Die neue Breite der Schaltfläche in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die standardmäßige Klasse-Implementierung ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) durch Aktualisieren die Größe und Position des internen `CMFCToolBarDateTimeCtrlImpl` Objekt.

##  <a name="onupdatetooltip"></a>  CMFCToolBarDateTimeCtrl::OnUpdateToolTip

Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Das übergeordnete Fenster.

*iButtonIndex*<br/>
[in] Der nullbasierte Index der Schaltfläche in der Auflistung der Schaltflächen übergeordnete Element.

*wndToolTip*<br/>
[in] Das Steuerelement, das den QuickInfo-Text anzeigt.

*str*<br/>
[out] Ein `CString` Objekt, das den aktualisierten QuickInfo-Text empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode den QuickInfo-Text aktualisiert; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) durch Anzeigen des QuickInfo-Texts, der mit der Schaltfläche zugeordnet ist. Wenn die Schaltfläche nicht horizontal angedockt ist, wird diese Methode führt keine Aktion aus und gibt FALSE zurück.

##  <a name="settime"></a>  CMFCToolBarDateTimeCtrl::SetTime

Legt das Datum und die in der / Zeitauswahl-Steuerelement fest.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Parameter

*timeNew*<br/>
[in] In der ersten Version, die einen Verweis auf eine [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden. In der zweiten Version, ein Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden.

*pTimeNew*<br/>
[in] Ein Zeiger auf die [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die die Zeit enthält, auf den das Steuerelement festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Legt die Zeit in einem Datums- / Zeitauswahl-Steuerelement fest, durch den Aufruf [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).

##  <a name="settimeall"></a>  CMFCToolBarDateTimeCtrl::SetTimeAll

Legt das Datum und die in der alle Instanzen der / Zeitauswahl-Steuerelement mit einer angegebenen Befehls-ID.

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
[in] Gibt an, eine Symbolleisten-Befehlsschaltfläche-ID.

*timeNew*<br/>
[in] In der ersten Version einer [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden. In der zweiten Version, ein Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das den Zeitpunkt enthält, auf den das Steuerelement festgelegt werden.

*pTimeNew*<br/>
[in] Ein Zeiger auf die [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die die Zeit enthält, auf den das Steuerelement festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sucht nach einer Symbolleisten-Schaltfläche, mit der angegebenen Befehls-ID, und legt die Zeit in einem Datums- / Zeitauswahl-Steuerelement fest, durch den Aufruf [CMFCToolBarDateTimeCtrl::SetTime](#settime).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



