---
title: COleControlSite-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
ms.openlocfilehash: 9b9b68a001acdf4b08d9cfc01cc67c43217d9a57
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504314"
---
# <a name="colecontrolsite-class"></a>COleControlSite-Klasse

Stellt Unterstützung für benutzerdefinierte clientseitige Steuerelement-Schnittstellen bereit.

## <a name="syntax"></a>Syntax

```
class COleControlSite : public CCmdTarget
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleControlSite::COleControlSite](#colecontrolsite)|Erstellt ein `COleControlSite`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|Bindet die Standard Eigenschaft des gehosteten Steuer Elements an eine Datenquelle.|
|[COleControlSite::BindProperty](#bindproperty)|Bindet eine Eigenschaft des gehosteten Steuer Elements an eine Datenquelle.|
|[COleControlSite::CreateControl](#createcontrol)|Erstellt ein gehostetes ActiveX-Steuerelement.|
|[COleControlSite::DestroyControl](#destroycontrol)|Zerstört das gehostete-Steuerelement.|
|[COleControlSite::DoVerb](#doverb)|Führt ein bestimmtes Verb des gehosteten Steuer Elements aus.|
|[COleControlSite::EnableDSC](#enabledsc)|Ermöglicht die Datenbeschaffung für eine Steuerungs Site.|
|[COleControlSite::EnableWindow](#enablewindow)|Aktiviert die Steuerungs Website.|
|[COleControlSite::FreezeEvents](#freezeevents)|Gibt an, ob die Steuerelement Site Ereignisse annimmt.|
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Ruft den Standard Schaltflächen Code für das gehostete Steuerelement ab.|
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Ruft den Bezeichner des Steuer Elements ab.|
|[COleControlSite::GetEventIID](#geteventiid)|Ruft die ID einer Ereignis Schnittstelle für ein gehostetes Steuerelement ab.|
|[COleControlSite::GetExStyle](#getexstyle)|Ruft die erweiterten Stile der Steuerelement Website ab.|
|[COleControlSite::GetProperty](#getproperty)|Ruft eine bestimmte Eigenschaft des gehosteten Steuer Elements ab.|
|[COleControlSite::GetStyle](#getstyle)|Ruft die Stile der Steuerelement Website ab.|
|[COleControlSite::GetWindowText](#getwindowtext)|Ruft den Text des gehosteten Steuer Elements ab.|
|[COleControlSite::InvokeHelper](#invokehelper)|Rufen Sie eine bestimmte Methode des gehosteten Steuer Elements auf.|
|[COleControlSite::InvokeHelperV](#invokehelperv)|Rufen Sie eine bestimmte Methode des gehosteten Steuer Elements mit einer Variablen Liste von Argumenten auf.|
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Bestimmt, ob das-Steuerelement die Standard Schaltfläche im-Fenster ist.|
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Überprüft den sichtbaren Zustand der Steuerungs Website.|
|[COleControlSite::ModifyStyle](#modifystyle)|Ändert die aktuellen erweiterten Stile der Steuerelement Website.|
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Ändert die aktuellen Stile der Steuerelement Website.|
|[COleControlSite::MoveWindow](#movewindow)|Ändert die Position der Steuerelement Website.|
|[COleControlSite::QuickActivate](#quickactivate)|Aktiviert das gehostete Steuerelement schnell.|
|[COleControlSite::SafeSetProperty](#safesetproperty)|Legt eine Eigenschaft oder Methode des Steuer Elements fest, ohne dass eine Ausnahme ausgelöst werden soll.|
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Legt die Standard Schaltfläche im Fenster fest.|
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Ruft den Bezeichner des Steuer Elements ab.|
|[COleControlSite::SetFocus](#setfocus)|Legt den Fokus auf die Steuerungs Website fest.|
|[COleControlSite::SetProperty](#setproperty)|Legt eine bestimmte Eigenschaft des gehosteten Steuer Elements fest.|
|[COleControlSite::SetPropertyV](#setpropertyv)|Legt eine bestimmte Eigenschaft des gehosteten Steuer Elements mit einer Variablen Liste von Argumenten fest.|
|[COleControlSite::SetWindowPos](#setwindowpos)|Legt die Position der Steuerelement Website fest.|
|[COleControlSite::SetWindowText](#setwindowtext)|Legt den Text des gehosteten Steuer Elements fest.|
|[COleControlSite::ShowWindow](#showwindow)|Zeigt die Steuerelement Website an oder blendet sie aus.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Ruft Tastatur Informationen und mnetmonics für das gehostete Steuerelement ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Bestimmt, ob das gehostete Steuerelement ein fensterloses Steuerelement ist.|
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Enthält Informationen zur Tastatur Behandlung für das-Steuerelement.|
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Das Cookie des Verbindungs Punkts des Steuer Elements.|
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Die verschiedenen Zustände für das gehostete Steuerelement.|
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|Das `IPropertyNotifySink` Cookie des Steuer Elements.|
|[COleControlSite::m_dwStyle](#m_dwstyle)|Die Stile des gehosteten Steuer Elements.|
|[COleControlSite::m_hWnd](#m_hwnd)|Das Handle der Steuerelement Site.|
|[COleControlSite::m_iidEvents](#m_iidevents)|Die ID der Ereignis Schnittstelle für das gehostete Steuerelement.|
|[COleControlSite::m_nID](#m_nid)|Die ID des gehosteten Steuer Elements.|
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Ein Zeiger auf das `IOleInPlaceActiveObject` -Objekt des gehosteten Steuer Elements.|
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Der Container des gehosteten Steuer Elements.|
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Ein Zeiger auf das `IOleInPlaceObject` -Objekt des gehosteten Steuer Elements.|
|[COleControlSite::m_pObject](#m_pobject)|Ein Zeiger auf die `IOleObjectInterface` -Schnittstelle des Steuer Elements.|
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Ein Zeiger auf die `IOleInPlaceObjectWindowless` -Schnittstelle des Steuer Elements.|
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Ein Zeiger auf das Fenster Objekt für das gehostete-Steuerelement.|
|[COleControlSite::m_rect](#m_rect)|Die Dimensionen der Steuerelement Site.|

## <a name="remarks"></a>Hinweise

Diese Unterstützung ist die primäre Methode, mit der ein eingebettetes ActiveX-Steuerelement Informationen über den Speicherort und den Umfang seiner Anzeige Site, seinen Moniker, seine Benutzeroberfläche, seine Umgebungs Eigenschaften und andere Ressourcen erhält, die von seinem Container bereitgestellt werden. `COleControlSite`implementiert die Schnittstellen `IBoundObjectSite` `INotifyDBEvents` [iolecontrolsite](/windows/win32/api/ocidl/nn-ocidl-iolecontrolsite), [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite), [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink),, und [IRowsetNotify](../../data/oledb/irowsetnotifyimpl-class.md) vollständig. Außerdem wird die IDispatch-Schnittstelle (Unterstützung für Umgebungs Eigenschaften und Ereignis senken) ebenfalls implementiert.

Um eine ActiveX-Steuerelement Site `COleControlSite`mithilfe von zu erstellen, `COleControlSite`leiten Sie eine Klasse von ab. Überschreiben `CWnd`Sie in der von abgeleiteten Klasse für den Container (beispielsweise das Dialogfeld `CWnd::CreateControlSite` ) die Funktion.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlSite`

## <a name="requirements"></a>Anforderungen

**Header:** afxocc. h

##  <a name="binddefaultproperty"></a>COleControlSite:: BindDefaultProperty

Bindet die in der Typbibliothek markierte standardmäßige einfache gebundene Eigenschaft des aufrufenden Objekts an den zugrunde liegenden Cursor, der durch die Eigenschaften DataSource, username, Password und SQL des Datenquellen-Steuer Elements definiert wird.

```
virtual void BindDefaultProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    LPCTSTR szFieldName,
    CWnd* pDSCWnd);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die DISPID einer Eigenschaft in einem Daten gebundenen Steuerelement an, das an ein Datenquellen-Steuerelement gebunden werden soll.

*vtProp*<br/>
Gibt den Typ der Eigenschaft an, die gebunden werden soll, z. –. VT_BSTR, VT_VARIANT usw.

*szFieldName*<br/>
Gibt den Namen der Spalte in dem Cursor an, der vom Datenquellen-Steuerelement bereitgestellt wird, an das die Eigenschaft gebunden wird.

*pDSCWnd*<br/>
Ein Zeiger auf das `CWnd`von abgeleitete Objekt, das das Datenquellen-Steuerelement hostet, an das die Eigenschaft gebunden wird.

### <a name="remarks"></a>Hinweise

Das `CWnd` Objekt, für das Sie diese Funktion aufzurufen, muss ein Daten gebundenes Steuerelement sein.

##  <a name="bindproperty"></a>COleControlSite:: BindProperty

Bindet die in der Typbibliothek markierte einfache gebundene Eigenschaft des aufrufenden Objekts an den zugrunde liegenden Cursor, der durch die Eigenschaften DataSource, username, Password und SQL des Datenquellen-Steuer Elements definiert wird.

```
virtual void BindProperty(
    DISPID dwDispId,
    CWnd* pWndDSC);
```

### <a name="parameters"></a>Parameter

*dwDispId*<br/>
Gibt die DISPID einer Eigenschaft in einem Daten gebundenen Steuerelement an, das an ein Datenquellen-Steuerelement gebunden werden soll.

*pWndDSC*<br/>
Ein Zeiger auf das `CWnd`von abgeleitete Objekt, das das Datenquellen-Steuerelement hostet, an das die Eigenschaft gebunden wird.

### <a name="remarks"></a>Hinweise

Das `CWnd` Objekt, für das Sie diese Funktion aufzurufen, muss ein Daten gebundenes Steuerelement sein.

##  <a name="colecontrolsite"></a>COleControlSite:: COleControlSite

Erstellt ein neues `COleControlSite`-Objekt.

```
explicit COleControlSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Parameter

*pCtrlCont*<br/>
Ein Zeiger auf den Container des Steuer Elements (das das Fenster darstellt, das das ativex-Steuerelement hostet).

### <a name="remarks"></a>Hinweise

Diese Funktion wird von der Funktion " [COccManager:: kreatecontainer](../../mfc/reference/coccmanager-class.md#createcontainer) " aufgerufen. Weitere Informationen zum Anpassen der Erstellung von Containern finden Sie unter " [COccManager:: anlagesite](../../mfc/reference/coccmanager-class.md#createsite)".

##  <a name="createcontrol"></a>COleControlSite:: kreatecontrol

Erstellt ein ActiveX-Steuerelement, das `COleControlSite` vom-Objekt gehostet wird.

```
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);

virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>Parameter

*pWndCtrl*<br/>
Ein Zeiger auf das Fenster Objekt, das das Steuerelement darstellt.

*clsid*<br/>
Die eindeutige Klassen-ID des Steuer Elements.

*lpszWindowName*<br/>
Ein Zeiger auf den Text, der im-Steuerelement angezeigt werden soll. Legt den Wert der Beschriftungs-oder Text Eigenschaft von winodw fest (sofern vorhanden).

*dwStyle*<br/>
Windows-Stile. Die verfügbaren Stile sind im Abschnitt " **Hinweise** " aufgeführt.

*Rect*<br/>
Gibt die Größe und Position des Steuer Elements an. Dies kann entweder ein `CRect` -Objekt oder eine `RECT` -Struktur sein.

*nID*<br/>
Gibt die untergeordnete Fenster-ID des Steuer Elements an.

*pPersist*<br/>
Ein Zeiger auf einen `CFile` , der den persistenten Zustand für das Steuerelement enthält. Der Standardwert ist NULL, was bedeutet, dass das Steuerelement selbst initialisiert wird, ohne seinen Zustand aus einem persistenten Speicher wiederherzustellen. Wenn nicht NULL, sollte es sich um einen Zeiger auf `CFile`ein von abgeleitetes Objekt handeln, das die persistenten Daten des Steuer Elements in Form eines Datenstroms oder eines Speichers enthält. Diese Daten wurden möglicherweise bei einer früheren Aktivierung des Clients gespeichert. Der `CFile` kann andere Daten enthalten, muss jedoch zum Zeitpunkt des `CreateControl`Aufrufes auf das erste Byte der persistenten Daten festgelegt sein.

*bStorage*<br/>
Gibt an, ob die Daten in *ppersistent* als `IStorage` -oder `IStream` -Daten interpretiert werden sollen. Wenn es sich bei den *ppersistent* -Daten um einen Speicher handelt, sollte *bstorage* den Wert true haben. Wenn es sich bei den *ppersistent* -Daten um einen Stream handelt, sollte *bstorage* den Wert false aufweisen. Der Standardwert ist false.

*bstrLicKey*<br/>
Optionale Lizenzschlüssel Daten. Diese Daten werden nur zum Erstellen von Steuerelementen benötigt, für die ein Laufzeitlizenz Schlüssel erforderlich ist. Wenn das Steuerelement die Lizenzierung unterstützt, müssen Sie einen Lizenzschlüssel bereitstellen, damit die Erstellung des Steuer Elements erfolgreich ist. Der Standardwert ist NULL.

*ppt*<br/>
Ein Zeiger auf eine `POINT` -Struktur, die die linke obere Ecke des-Steuer Elements enthält. Die Größe des Steuer Elements wird durch den Wert von *Psize*bestimmt. Die *PPT* -und *Psize* -Werte sind eine optionale Methode zum Angeben der Größe und Position des Steuer Elements.

*psize*<br/>
Ein Zeiger auf eine `SIZE` -Struktur, die die Größe des-Steuer Elements enthält. Die linke obere Ecke wird durch den Wert von *PPT*bestimmt. Die *PPT* -und *Psize* -Werte sind eine optionale Methode zum Angeben der Größe und Position des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Nur eine Teilmenge der Windows *dwstyle* -Flags wird unterstützt `CreateControl`von:

- WS_VISIBLE erstellt ein Fenster, das anfänglich sichtbar ist. Erforderlich, wenn das Steuerelement sofort sichtbar sein soll, wie z. b. gewöhnliche Fenster.

- WS_DISABLED erstellt ein Fenster, das anfänglich deaktiviert ist. Ein deaktiviertes Fenster kann keine Eingaben vom Benutzer empfangen. Kann festgelegt werden, wenn das Steuerelement über eine aktivierte Eigenschaft verfügt.

- WS_BORDER erstellt ein Fenster mit einem schmalen Rahmen. Kann festgelegt werden, wenn das Steuerelement eine BorderStyle-Eigenschaft aufweist.

- WS_GROUP gibt das erste Steuerelement einer Gruppe von Steuerelementen an. Der Benutzer kann den Tastaturfokus mithilfe der Richtungs Tasten von einem Steuerelement in der Gruppe zur nächsten ändern. Alle Steuerelemente, die nach dem ersten Steuerelement mit dem WS_GROUP-Stil definiert sind, gehören zur selben Gruppe. Das nächste Steuerelement mit dem WS_GROUP-Stil beendet die Gruppe und startet die nächste Gruppe.

- WS_TABSTOP gibt ein Steuerelement an, das den Tastaturfokus erhalten kann, wenn der Benutzer die Tab-Taste drückt. Wenn Sie die Tab-Taste drücken, wird der Tastaturfokus auf das nächste Steuerelement des WS_TABSTOP-Stils geändert.

Verwenden Sie die zweite Überladung, um Steuerelemente mit Standardgrößen zu erstellen.

##  <a name="destroycontrol"></a>COleControlSite::D estroycontrol

Zerstört das `COleControlSite`-Objekt.

```
virtual BOOL DestroyControl();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Sobald der Vorgang abgeschlossen ist, wird das Objekt aus dem Arbeitsspeicher freigegeben, und alle Zeiger auf das Objekt sind nicht mehr gültig.

##  <a name="doverb"></a>COleControlSite::D overb

Führt das angegebene Verb aus.

```
virtual HRESULT DoVerb(
    LONG nVerb,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>Parameter

*nVerb*<br/>
Gibt das auszuführende Verb an. Dies kann einen der folgenden einschließen:

|Wert|Bedeutung|Symbol|
|-----------|-------------|------------|
|0|Primäres Verb|OLEIVERB_PRIMARY|
|-1|Sekundäres Verb|(Keine)|
|1|Zeigt das Objekt zum Bearbeiten an.|OLEIVERB_SHOW|
|-2|Bearbeitet das Element in einem separaten Fenster.|OLEIVERB_OPEN|
|-3|Blendet das-Objekt aus.|OLEIVERB_HIDE|
|-4|Aktiviert ein Steuerelement direkt.|OLEIVERB_UIACTIVATE|
|-5|Aktiviert ein Steuerelement direkt, ohne dass zusätzliche Benutzeroberflächen Elemente vorhanden sind.|OLEIVERB_INPLACEACTIVATE|
|-7|Zeigen Sie die Eigenschaften des Steuer Elements an.|OLEIVERB_PROPERTIES|

*lpMsg*<br/>
Ein Zeiger auf die Meldung, die bewirkt hat, dass das Element aktiviert wurde.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft direkt über die- `IOleObject` Schnittstelle des Steuer Elements auf, um das angegebene Verb auszuführen. Wenn eine Ausnahme als Ergebnis dieses Funktions Aufrufes ausgelöst wird, wird ein HRESULT-Fehlercode zurückgegeben.

Weitere Informationen finden Sie unter [IOleObject::D overb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) in der Windows SDK.

##  <a name="enabledsc"></a>COleControlSite:: enabledsc

Ermöglicht die Datenbeschaffung für die Steuerungs Website.

```
virtual void EnableDSC();
```

### <a name="remarks"></a>Hinweise

Wird von Framework aufgerufen, um die Datenbeschaffung für die Steuerungs Site zu aktivieren und zu initialisieren. Überschreiben Sie diese Funktion, um angepasste Verhalten bereitzustellen.

##  <a name="enablewindow"></a>COleControlSite:: EnableWindow

Aktiviert oder deaktiviert die Maus-und Tastatureingaben auf der Steuerelement Website.

```
virtual BOOL EnableWindow(BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
Gibt an, ob das Fenster aktiviert oder deaktiviert werden soll: TRUE, wenn die Fenster Eingabe aktiviert werden soll, andernfalls false.

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn das Fenster zuvor deaktiviert wurde, andernfalls 0.

##  <a name="freezeevents"></a>COleControlSite:: frezeevents

Gibt an, ob die Steuerelement Site Ereignisse behandelt oder ignoriert, die von einem Steuerelement ausgelöst werden.

```
void FreezeEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Parameter

*bFreeze*<br/>
Gibt an, ob die Steuerelementsite das Akzeptieren von Ereignissen beenden möchte. Ungleich 0 (null), wenn das Steuerelement keine Ereignisse annimmt. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn *bfreeze* den Wert true hat, fordert die Steuerungs Website das Steuerelement auf, Ereignisse zu verhindern. Wenn *bfreeze* den Wert false hat, fordert die Steuerungs Website das Steuerelement auf, das Auslösen von Ereignissen fortzusetzen.

> [!NOTE]
>  Das Steuerelement ist nicht erforderlich, um das Auslösen von Ereignissen zu verhindern, wenn es von der Steuerungs Website angefordert wird Die Anwendung kann weiterhin ausgelöst werden, aber alle nachfolgenden Ereignisse werden von der Steuerungs Website ignoriert.

##  <a name="getcontrolinfo"></a>COleControlSite:: GetControlInfo

Ruft Informationen über die Tastatur-mnetmonics und das Tastatur Verhalten eines Steuer Elements ab.

```
void GetControlInfo();
```

### <a name="remarks"></a>Hinweise

Die Informationen werden in [COleControlSite:: m_ctlInfo](#m_ctlinfo)gespeichert.

##  <a name="getdefbtncode"></a>COleControlSite:: getdefbtncode

Bestimmt, ob das Steuerelement eine Standard-pushschaltfläche ist.

```
DWORD GetDefBtnCode();
```

### <a name="return-value"></a>Rückgabewert

Kann einer der folgenden Werte sein:

- Das DLGC_DEFPUSHBUTTON-Steuerelement ist die Standard Schaltfläche im Dialogfeld.

- Das DLGC_UNDEFPUSHBUTTON-Steuerelement ist nicht die Standard Schaltfläche im Dialogfeld.

- **0** -Steuerelement ist keine Schaltfläche.

##  <a name="getdlgctrlid"></a>COleControlSite:: getdlgctrlid

Ruft den Bezeichner des Steuer Elements ab.

```
virtual int GetDlgCtrlID() const;
```

### <a name="return-value"></a>Rückgabewert

Der Bezeichner des Dialog Felds für das-Steuerelement.

##  <a name="geteventiid"></a>COleControlSite:: geteventiid

Ruft einen Zeiger auf die Standard Ereignis Schnittstelle des-Steuer Elements ab.

```
BOOL GetEventIID(IID* piid);
```

### <a name="parameters"></a>Parameter

*piid*<br/>
Ein Zeiger auf eine Schnittstellen-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn erfolgreich, andernfalls 0. Bei erfolgreicher Ausführung enthält *piid* die Schnittstellen-ID für die Standard Ereignis Schnittstelle des Steuer Elements.

##  <a name="getexstyle"></a>COleControlSite:: getexstyle

Ruft die erweiterten Stile des Fensters ab.

```
virtual DWORD GetExStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Die erweiterten Stile des Steuerelement Fensters.

### <a name="remarks"></a>Hinweise

Rufen Sie zum Abrufen der regulären Stile [COleControlSite:: GetStyle](#getstyle)auf.

##  <a name="getproperty"></a>COleControlSite:: GetProperty

Ruft die von *dwdispid*angegebene Steuerelement Eigenschaft ab.

```
virtual void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Dispatch-ID der Eigenschaft an, die auf der Standard `IDispatch` Schnittstelle des Steuer Elements abgerufen wird, die abgerufen werden soll.

*vtProp*<br/>
Gibt den Typ der abzurufenden Eigenschaft an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvProp*<br/>
Adresse der Variablen, die den Eigenschafts Wert empfängt. Er muss mit dem von *vtprop*angegebenen Typ identisch sein.

### <a name="remarks"></a>Hinweise

Der Wert wird durch " *pvprop*" zurückgegeben.

##  <a name="getstyle"></a>COleControlSite:: GetStyle

Ruft die Stile der Steuerelement Website ab.

```
virtual DWORD GetStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Die Fenster Stile.

### <a name="remarks"></a>Hinweise

Eine Liste möglicher Werte finden Sie unter [Windows-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Rufen Sie [COleControlSite:: getexstyle](#getexstyle)auf, um die erweiterten Stile der Steuerelement Website abzurufen.

##  <a name="getwindowtext"></a>COleControlSite:: GetWindowText

Ruft den aktuellen Text des-Steuer Elements ab.

```
virtual void GetWindowText(CString& str) const;
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein `CString` -Objekt, das den aktuellen Text des-Steuer Elements enthält.

### <a name="remarks"></a>Hinweise

Wenn das Steuerelement die Eigenschaft für die Beschriftungs Eigenschaft unterstützt, wird dieser Wert zurückgegeben. Wenn die Eigenschaft für die Beschriftungs Eigenschaft nicht unterstützt wird, wird der Wert für die Text-Eigenschaft zurückgegeben.

##  <a name="invokehelper"></a>COleControlSite:: InvokeHelper

Ruft die von *dwdispid*angegebene Methode oder Eigenschaft in dem von *wFlags*angegebenen Kontext auf.

```
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Identifiziert die Dispatch-ID der Eigenschaft oder Methode, die auf der- `IDispatch` Schnittstelle des Steuer Elements gefunden wird, die aufgerufen werden soll.

*wFlags*<br/>
Flags, die den Kontext des Aufrufs von IDispatch:: Aufrufen beschreiben. Mögliche *wFlags* -Werte finden `IDispatch::Invoke` Sie unter in der Windows SDK.

*vtRet*<br/>
Gibt den Typ des Rückgabewerts an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvRet*<br/>
Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Er muss mit dem Typ identisch sein, der von *vtret*angegeben wird.

*pbParamInfo*<br/>
Zeiger auf eine mit NULL endenden Byte Zeichenfolge, die die Typen der Parameter nach *pbparaminfo*angibt. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Variable Parameterliste, der in *pbparaminfo*angegebenen Typen.

### <a name="remarks"></a>Hinweise

Der *pbparaminfo* -Parameter gibt die Typen der Parameter an, die an die Methode oder Eigenschaft übergeben werden. Die Variablen Liste der Argumente wird durch... in der Syntax Deklaration.

Diese Funktion konvertiert die Parameter in VARIANTARG-Werte und ruft dann `IDispatch::Invoke` die-Methode für das-Steuerelement auf. Bei einem Fehler des Aufrufs von `IDispatch::Invoke` löst diese Funktion eine Ausnahme aus. Wenn der von zurückgegebene Status `IDispatch::Invoke` Code `DISP_E_EXCEPTION`ist, löst diese Funktion `COleDispatchException` ein-Objekt aus, andernfalls `COleException`wird eine ausgelöst.

##  <a name="invokehelperv"></a>COleControlSite:: invokehelperv

Ruft die von *dwdispid*angegebene Methode oder Eigenschaft in dem von *wFlags*angegebenen Kontext auf.

```
virtual void InvokeHelperV(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo,
    va_list argList);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Identifiziert die Dispatch-ID der Eigenschaft oder Methode, die auf der- `IDispatch` Schnittstelle des Steuer Elements gefunden wird, die aufgerufen werden soll.

*wFlags*<br/>
Flags, die den Kontext des Aufrufs von IDispatch:: Aufrufen beschreiben.

*vtRet*<br/>
Gibt den Typ des Rückgabewerts an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvRet*<br/>
Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Er muss mit dem Typ identisch sein, der von *vtret*angegeben wird.

*pbParamInfo*<br/>
Zeiger auf eine mit NULL endenden Byte Zeichenfolge, die die Typen der Parameter nach *pbparaminfo*angibt. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*argList*<br/>
Zeiger auf eine Variablen Argumentliste.

### <a name="remarks"></a>Hinweise

Der *pbparaminfo* -Parameter gibt die Typen der Parameter an, die an die Methode oder Eigenschaft übergeben werden. Zusätzliche Parameter für die aufgerufene Methode oder Eigenschaft können mithilfe des *va_list* -Parameters übergeben werden.

In der Regel wird diese Funktion von `COleControlSite::InvokeHelper`aufgerufen.

##  <a name="isdefaultbutton"></a>COleControlSite:: isDefaultButton

Bestimmt, ob das Steuerelement die Standard Schaltfläche ist.

```
BOOL IsDefaultButton();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Steuerelement die Standard Schaltfläche im Fenster ist, andernfalls NULL.

##  <a name="iswindowenabled"></a>COleControlSite:: iswindowenabled

Bestimmt, ob die Steuerelement Site aktiviert ist.

```
virtual BOOL IsWindowEnabled() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Steuerelement aktiviert ist, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Der Wert wird aus der vordefinierten Eigenschaft des Steuer Elements abgerufen.

##  <a name="m_biswindowless"></a>COleControlSite:: m_bIsWindowless

Bestimmt, ob das Objekt ein fensterloses Steuerelement ist.

```
BOOL m_bIsWindowless;
```

### <a name="remarks"></a>Hinweise

Ein Wert ungleich 0 (null), wenn das Steuerelement kein Fenster hat, andernfalls NULL

##  <a name="m_ctlinfo"></a>COleControlSite:: m_ctlInfo

Informationen zum Behandeln von Tastatureingaben durch das Steuerelement.

```
CONTROLINFO m_ctlInfo;
```

### <a name="remarks"></a>Hinweise

Diese Informationen werden in einer [controlInfo](/windows/win32/api/ocidl/ns-ocidl-controlinfo) -Struktur gespeichert.

##  <a name="m_dweventsink"></a>COleControlSite:: m_dwEventSink

Enthält das Cookie des Verbindungs Punkts aus der Ereignis Senke des Steuer Elements.

```
DWORD m_dwEventSink;
```

##  <a name="m_dwmiscstatus"></a>COleControlSite:: m_dwMiscStatus

Enthält verschiedene Informationen über das-Steuerelement.

```
DWORD m_dwMiscStatus;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc)in der Windows SDK.

##  <a name="m_dwpropnotifysink"></a>COleControlSite:: m_dwPropNotifySink

Enthält das [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) -Cookie.

```
DWORD m_dwPropNotifySink;
```

##  <a name="m_dwstyle"></a>COleControlSite:: m_dwStyle

Enthält die Fenster Stile des-Steuer Elements.

```
DWORD m_dwStyle;
```

##  <a name="m_hwnd"></a>COleControlSite:: m_hWnd

Enthält das HWND des Steuer Elements oder NULL, wenn es sich um ein fensterloses Steuerelement handelt.

```
HWND m_hWnd;
```

##  <a name="m_iidevents"></a>COleControlSite:: m_iidEvents

Enthält die Schnittstellen-ID der standardmäßigen Ereignis Senke-Schnittstelle des Steuer Elements.

```
IID m_iidEvents;
```

##  <a name="m_nid"></a>COleControlSite:: m_nID

Enthält die Dialogfeld Element-ID des Steuer Elements.

```
UINT m_nID;
```

##  <a name="m_pactiveobject"></a>COleControlSite:: m_pActiveObject

Enthält die [IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) -Schnittstelle des Steuer Elements.

```
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;
```

##  <a name="m_pctrlcont"></a>COleControlSite:: m_pCtrlCont

Enthält den Container des Steuer Elements (darstellt das Formular).

```
COleControlContainer* m_pCtrlCont;
```

##  <a name="m_pinplaceobject"></a>COleControlSite:: m_pInPlaceObject

Enthält die `IOleInPlaceObject` [IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) -Schnittstelle des Steuer Elements.

```
LPOLEINPLACEOBJECT m_pInPlaceObject;
```

##  <a name="m_pobject"></a>COleControlSite:: m_pObject

Enthält die `IOleObjectInterface` -Schnittstelle des Steuer Elements.

```
LPOLEOBJECT m_pObject;
```

##  <a name="m_pwindowlessobject"></a>COleControlSite:: m_pWindowlessObject

Enthält die `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) -Schnittstelle des Steuer Elements.

```
IOleInPlaceObjectWindowless* m_pWindowlessObject;
```

##  <a name="m_pwndctrl"></a>COleControlSite:: m_pWndCtrl

Enthält einen Zeiger auf das `CWnd` -Objekt, das das Steuerelement selbst darstellt.

```
CWnd* m_pWndCtrl;
```

##  <a name="m_rect"></a>COleControlSite:: m_rect

Enthält die Begrenzungen des Steuer Elements relativ zum Fenster des Containers.

```
CRect m_rect;
```

##  <a name="modifystyle"></a>COleControlSite:: modifystyle

Ändert die Stile des-Steuer Elements.

```
virtual BOOL ModifyStyle(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

*dwRemove*<br/>
Die Stile, die aus den aktuellen Fenster Stilen entfernt werden sollen.

*dwAdd*<br/>
Die Stile, die aus den aktuellen Fenster Stilen hinzugefügt werden sollen.

*nFlags*<br/>
Fenster positionierungsflags. Eine Liste möglicher Werte finden Sie unter der [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) -Funktion in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Stile geändert werden, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Die vordefinierte Eigenschaft des Steuer Elements wird entsprechend der Einstellung für WS_DISABLED geändert. Die Eigenschaften des Steuer Elements im Rahmen des Steuer Elements wird entsprechend der angeforderten Einstellung für WS_BORDER geändert. Alle anderen Stile werden direkt auf das Fenster Handle des Steuer Elements angewendet, sofern ein solches vorhanden ist.

Ändert die Fenster Stile des-Steuer Elements. Stile, die hinzugefügt oder entfernt werden sollen, können mithilfe des bitweisen or ( &#124; )-Operators kombiniert werden. Informationen zu den verfügbaren Fenster Stilen finden Sie [in der Windows SDK-Funktion in](/windows/win32/api/winuser/nf-winuser-createwindoww) der-.

Wenn *nFlags* ungleich NULL ist, `ModifyStyle` Ruft die Win32- `SetWindowPos`Funktion auf und zeichnet das Fenster neu, indem *nFlags* mit den folgenden vier Flags kombiniert werden:

- SWP_NOSIZE behält die aktuelle Größe bei.

- SWP_NOMOVE behält die aktuelle Position bei.

- SWP_NOZORDER behält die aktuelle Z-Reihenfolge bei.

- SWP_NOACTIVATE aktiviert das Fenster nicht.

Um die erweiterten Stile eines Fensters zu ändern, müssen Sie [modifystyleex](#modifystyleex)aufrufen.

##  <a name="modifystyleex"></a>COleControlSite:: modifystyleex

Ändert die erweiterten Stile des-Steuer Elements.

```
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

*dwRemove*<br/>
Die erweiterten Stile, die aus den aktuellen Fenster Stilen entfernt werden sollen.

*dwAdd*<br/>
Die erweiterten Stile, die aus den aktuellen Fenster Stilen hinzugefügt werden sollen.

*nFlags*<br/>
Fenster positionierungsflags. Eine Liste möglicher Werte finden Sie unter der [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) -Funktion in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Stile geändert werden, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Die Stock-Darstellungs Eigenschaft des Steuer Elements wird entsprechend der-Einstellung für WS_EX_CLIENTEDGE geändert. Alle anderen erweiterten Fenster Stile werden direkt auf das Fenster Handle des Steuer Elements angewendet, sofern ein solches vorhanden ist.

Ändert das Fenster Erweiterte Stile des Steuerelement-Website Objekts. Stile, die hinzugefügt oder entfernt werden sollen, können mithilfe des bitweisen or ( &#124; )-Operators kombiniert werden. Informationen zu den verfügbaren Fenster Stilen finden [Sie unter der Funktion "](/windows/win32/api/winuser/nf-winuser-createwindowexw) Funktion" in der Windows SDK.

Wenn *nFlags* ungleich NULL ist, `ModifyStyleEx` Ruft die Win32- `SetWindowPos`Funktion auf und zeichnet das Fenster neu, indem *nFlags* mit den folgenden vier Flags kombiniert werden:

- SWP_NOSIZE behält die aktuelle Größe bei.

- SWP_NOMOVE behält die aktuelle Position bei.

- SWP_NOZORDER behält die aktuelle Z-Reihenfolge bei.

- SWP_NOACTIVATE aktiviert das Fenster nicht.

Um die erweiterten Stile eines Fensters zu ändern, nennen Sie [modifystyle](#modifystyle).

##  <a name="movewindow"></a>COleControlSite:: muvewindow

Ändert die Position des-Steuer Elements.

```
virtual void MoveWindow(
    int x,
    int y,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die neue Position der linken Seite des Fensters.

*y*<br/>
Die neue Position des oberen Fenster Rands.

*nWidth*<br/>
Die neue Breite des Fensters.

*nheight*<br/>
Die neue Höhe des Fensters.

##  <a name="quickactivate"></a>COleControlSite:: quickaktivierung

Aktiviert das enthaltene Steuerelement schnell.

```
virtual BOOL QuickActivate();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Steuerungs Site aktiviert wurde, andernfalls 0 (null)

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur aufgerufen werden, wenn der Benutzer den Erstellungs Prozess des-Steuer Elements überschreibt.

Die `IPersist*::Load` - `IPersist*::InitNew` Methode und die-Methode sollten nach der schnellen Aktivierung aufgerufen werden. Das-Steuerelement sollte während der schnellen Aktivierung seine Verbindungen mit den senken des Containers herstellen. Diese Verbindungen sind jedoch erst dann aktiv, `IPersist*::Load` Wenn `IPersist*::InitNew` oder aufgerufen wurde.

##  <a name="safesetproperty"></a>COleControlSite:: safesetproperty

Legt die von *dwdispid*angegebene Steuerelement Eigenschaft fest.

```
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Dispatch-ID der Eigenschaft oder Methode an, die auf der- `IDispatch` Schnittstelle des Steuer Elements festgelegt werden soll.

*vtProp*<br/>
Gibt den Typ der festzulegenden Eigenschaft an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Ein einzelner Parameter des Typs, der von *vtprop*angegeben wird.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Wenn `SetProperty` ein `SetPropertyV`Fehler auftritt (z. b. Wenn Sie versuchen, eine nicht vorhandene Eigenschaft festzulegen), wird im Gegensatz zu und keine Ausnahme ausgelöst.

##  <a name="setdefaultbutton"></a>COleControlSite:: setDefaultButton

Legt das-Steuerelement als Standard Schaltfläche fest.

```
void SetDefaultButton(BOOL bDefault);
```

### <a name="parameters"></a>Parameter

*bDefault*<br/>
Ungleich NULL, wenn das Steuerelement die Standard Schaltfläche werden soll. andernfalls NULL.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Für das Steuerelement muss das OLEMISC_ACTSLIKEBUTTON-Statusbit festgelegt sein.

##  <a name="setdlgctrlid"></a>COleControlSite:: setdlgctrlid

Ändert den Wert des Dialogfeld Element-Bezeichners des-Steuer Elements.

```
virtual int SetDlgCtrlID(int nID);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Der neue Bezeichnerwert.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, der vorherige Dialogfeld Element Bezeichner des Fensters. andernfalls 0.

### <a name="remarks"></a>Hinweise

##  <a name="setfocus"></a>COleControlSite:: SetFocus

Legt den Fokus auf das-Steuerelement fest.

```
virtual CWnd* SetFocus();
virtual CWnd* SetFocus(LPMSG lpmsg);
```

### <a name="parameters"></a>Parameter

*lpmsg*<br/>
Ein Zeiger auf eine [MSG-Struktur](/windows/win32/api/winuser/ns-winuser-msg). Diese Struktur enthält die Windows-Meldung, `SetFocus` die die Anforderung für das Steuerelement auslöst, das in der aktuellen Steuerungs Site enthalten ist.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Fenster, das zuvor den Fokus hatte.

##  <a name="setproperty"></a>COleControlSite:: SetProperty

Legt die von *dwdispid*angegebene Steuerelement Eigenschaft fest.

```
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Dispatch-ID der Eigenschaft oder Methode an, die auf der- `IDispatch` Schnittstelle des Steuer Elements festgelegt werden soll.

*vtProp*<br/>
Gibt den Typ der festzulegenden Eigenschaft an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Ein einzelner Parameter des Typs, der von *vtprop*angegeben wird.

### <a name="remarks"></a>Hinweise

Wenn `SetProperty` auf einen Fehler stößt, wird eine Ausnahme ausgelöst.

Der Ausnahmetyp wird durch den Rückgabewert des Versuchs festgelegt, die Eigenschaft oder Methode festzulegen. Wenn der Rückgabewert ist `DISP_E_EXCEPTION`, wird `COleDispatchExcpetion` eine ausgelöst; andernfalls ein `COleException`-Wert.

##  <a name="setpropertyv"></a>COleControlSite:: setpropertyv

Legt die von *dwdispid*angegebene Steuerelement Eigenschaft fest.

```
virtual void SetPropertyV(
    DISPID dwDispID,
    VARTYPE vtProp,
    va_list argList);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Dispatch-ID der Eigenschaft oder Methode an, die auf der- `IDispatch` Schnittstelle des Steuer Elements festgelegt werden soll.

*vtProp*<br/>
Gibt den Typ der festzulegenden Eigenschaft an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*argList*<br/>
Zeiger auf die Liste der Argumente.

### <a name="remarks"></a>Hinweise

Zusätzliche Parameter für die aufgerufene Methode oder Eigenschaft können mithilfe des *arg_list* -Parameters als passeed verwendet werden. Wenn `SetProperty` auf einen Fehler stößt, wird eine Ausnahme ausgelöst.

Der Ausnahmetyp wird durch den Rückgabewert des Versuchs festgelegt, die Eigenschaft oder Methode festzulegen. Wenn der Rückgabewert ist `DISP_E_EXCEPTION`, wird `COleDispatchExcpetion` eine ausgelöst; andernfalls ein `COleException`-Wert.

##  <a name="setwindowpos"></a>COleControlSite:: SetWindowPos

Legt die Größe, Position und Z-Reihenfolge der Steuerelement Website fest.

```
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

*pWndInsertAfter*<br/>
Ein Zeiger auf das Fenster.

*w*<br/>
Die neue Position der linken Seite des Fensters.

*y*<br/>
Die neue Position des oberen Fenster Rands.

*verschoben*<br/>
Die neue Breite des Fensters.

*CY*<br/>
Die neue Höhe des Fensters.

*nFlags*<br/>
Gibt die Größenanpassung und Positionierung von Fenstern an. Mögliche Werte finden Sie im Abschnitt "Hinweise" für [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich, andernfalls 0 (null).

##  <a name="setwindowtext"></a>COleControlSite:: SetWindowText

Legt den Text für die Steuerelement Site fest.

```
virtual void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*lpszString*<br/>
Zeiger auf eine mit NULL endende Zeichenfolge, die als neuer Titel oder Steuerelement Text verwendet werden soll.

### <a name="remarks"></a>Hinweise

Diese Funktion versucht zunächst, die Beschriftungs Eigenschaft festzulegen. Wenn die Eigenschaft für die Beschriftungs Eigenschaft nicht unterstützt wird, wird stattdessen die Text-Eigenschaft festgelegt.

##  <a name="showwindow"></a>COleControlSite:: ShowWindow

Legt den Anzeige Zustand des Fensters fest.

```
virtual BOOL ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Parameter

*nCmdShow*<br/>
Gibt an, wie die Steuerelement Site angezeigt werden soll. Es muss sich um einen der folgenden Werte handeln:

- SW_HIDE blendet dieses Fenster aus und übergibt die Aktivierung an ein anderes Fenster.

- SW_MINIMIZE minimiert das Fenster und aktiviert das Fenster der obersten Ebene in der Liste des Systems.

- SW_RESTORE aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert ist, stellt Windows es in seiner ursprünglichen Größe und Position wieder her.

- SW_SHOW aktiviert das Fenster und zeigt es in seiner aktuellen Größe und Position an.

- SW_SHOWMAXIMIZED aktiviert das Fenster und zeigt es als maximiertes Fenster an.

- SW_SHOWMINIMIZED aktiviert das Fenster und zeigt es als Symbol an.

- SW_SHOWMINNOACTIVE zeigt das Fenster als Symbol an. Das aktuell aktive Fenster bleibt aktiv.

- SW_SHOWNA zeigt das Fenster in seinem aktuellen Zustand an. Das aktuell aktive Fenster bleibt aktiv.

- SW_SHOWNOACTIVATE zeigt das Fenster in seiner aktuellen Größe und Position an. Das aktuell aktive Fenster bleibt aktiv.

- SW_SHOWNORMAL aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert ist, stellt Windows es in seiner ursprünglichen Größe und Position wieder her.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Fenster zuvor sichtbar war. 0, wenn das Fenster zuvor ausgeblendet wurde.

## <a name="see-also"></a>Siehe auch

[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleControlContainer-Klasse](../../mfc/reference/colecontrolcontainer-class.md)
