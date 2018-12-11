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
ms.openlocfilehash: 26d0f5e875c4f3982705a2cf571b15cd5bfac985
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178919"
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
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|Die Standardeigenschaft des gehosteten Steuerelements bindet an eine Datenquelle.|
|[COleControlSite::BindProperty](#bindproperty)|Bindet eine Eigenschaft des gehosteten Steuerelements an eine Datenquelle an.|
|[COleControlSite::CreateControl](#createcontrol)|Erstellt ein gehostetes ActiveX-Steuerelement.|
|[COleControlSite::DestroyControl](#destroycontrol)|Zerstört das gehostete Steuerelement an.|
|[COleControlSite::DoVerb](#doverb)|Führt ein bestimmtes Verb des gehosteten Steuerelements.|
|[COleControlSite::EnableDSC](#enabledsc)|Ermöglicht die Daten, die als Quelle für eine Website des Steuerelements.|
|[COleControlSite::EnableWindow](#enablewindow)|Können die Website des Steuerelements.|
|[COleControlSite::FreezeEvents](#freezeevents)|Gibt an, wenn die Website des Steuerelements Ereignisse akzeptiert.|
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Ruft den Standardcode für die Schaltfläche für das gehostete Steuerelement ab.|
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Ruft den Bezeichner des Steuerelements ab.|
|[COleControlSite::GetEventIID](#geteventiid)|Ruft die ID einer Ereignis-Schnittstelle für ein gehostetes Steuerelement ab.|
|[COleControlSite::GetExStyle](#getexstyle)|Ruft die erweiterten Stile, der die Website des Steuerelements ab.|
|[COleControlSite::GetProperty](#getproperty)|Ruft eine bestimmte Eigenschaft des gehosteten Steuerelements ab.|
|[COleControlSite::GetStyle](#getstyle)|Ruft die Formatvorlagen der Site für das Steuerelement ab.|
|[COleControlSite::GetWindowText](#getwindowtext)|Ruft den Text des gehosteten Steuerelements ab.|
|[COleControlSite::InvokeHelper](#invokehelper)|Rufen Sie eine bestimmte Methode des gehosteten Steuerelements.|
|[COleControlSite::InvokeHelperV](#invokehelperv)|Rufen Sie eine bestimmte Methode des gehosteten Steuerelements mit einer Liste der Variablen der Argumente.|
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Bestimmt, ob das Steuerelement die Standardschaltfläche im Fenster ist.|
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Überprüft den Status angezeigten, der die Website des Steuerelements.|
|[COleControlSite::ModifyStyle](#modifystyle)|Ändert die aktuelle erweiterte Stile, der die Website des Steuerelements.|
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Ändert die aktuelle Stile, der die Website des Steuerelements an.|
|[COleControlSite::MoveWindow](#movewindow)|Ändert die Position von der Website des Steuerelements.|
|[COleControlSite::QuickActivate](#quickactivate)|Schnelle aktiviert das gehostete Steuerelement.|
|[COleControlSite::SafeSetProperty](#safesetproperty)|Legt eine Eigenschaft oder Methode des Steuerelements ohne Wahrscheinlichkeit, dass eine Ausnahme auszulösen.|
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Legt die Standardschaltfläche im Fenster fest.|
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Ruft den Bezeichner des Steuerelements ab.|
|[COleControlSite::SetFocus](#setfocus)|Legt den Fokus auf die Website des Steuerelements fest.|
|[COleControlSite::SetProperty](#setproperty)|Legt eine bestimmte Eigenschaft des gehosteten Steuerelements fest.|
|[COleControlSite::SetPropertyV](#setpropertyv)|Legt eine bestimmte Eigenschaft des gehosteten Steuerelements mit einer Liste von Argumenten der Variablen fest.|
|[COleControlSite::SetWindowPos](#setwindowpos)|Legt die Position der Website des Steuerelements fest.|
|[COleControlSite::SetWindowText](#setwindowtext)|Legt den Text des gehosteten Steuerelements fest.|
|[COleControlSite::ShowWindow](#showwindow)|Anzeigen oder Ausblenden der Website des Steuerelements.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Ruft Tastaturinformationen und mnemonischen Zeichen für das gehostete Steuerelement ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Bestimmt, ob das gehostete Steuerelement ein fensterloses Steuerelement befindet.|
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Enthält Informationen über die Tastatur, die Klassenbehandlung für das Steuerelement.|
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Das Cookie des Verbindungspunkts des Steuerelements.|
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Die verschiedenen Status für dieses Steuerelement.|
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|Die `IPropertyNotifySink` Cookie des Steuerelements.|
|[COleControlSite::m_dwStyle](#m_dwstyle)|Die Formate des gehosteten Steuerelements.|
|[COleControlSite::m_hWnd](#m_hwnd)|Der Handle für die Website des Steuerelements.|
|[COleControlSite::m_iidEvents](#m_iidevents)|Die ID der Ereignisschnittstelle für dieses Steuerelement.|
|[COleControlSite::m_nID](#m_nid)|Die ID des gehosteten Steuerelements.|
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Ein Zeiger auf die `IOleInPlaceActiveObject` Objekt des gehosteten Steuerelements.|
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Der Container des gehosteten Steuerelements.|
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Ein Zeiger auf die `IOleInPlaceObject` Objekt des gehosteten Steuerelements.|
|[COleControlSite::m_pObject](#m_pobject)|Ein Zeiger auf die `IOleObjectInterface` Schnittstelle des Steuerelements.|
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Ein Zeiger auf die `IOleInPlaceObjectWindowless` Schnittstelle des Steuerelements.|
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Ein Zeiger auf das Window-Objekt, für das gehostete Steuerelement.|
|[COleControlSite::m_rect](#m_rect)|Die Dimensionen von der Website des Steuerelements.|

## <a name="remarks"></a>Hinweise

Diese Unterstützung ist das primäre Mittel, mit dem ein eingebettetes ActiveX-Steuerelement ruft Informationen über den Speicherort und den Umfang der anzeigensite, des Monikers, seine Benutzeroberfläche, die ambient-Eigenschaften und andere Ressourcen, die vom Container bereitgestellt werden ab. `COleControlSite` vollständig implementiert die [IOleControlSite](/windows/desktop/api/ocidl/nn-ocidl-iolecontrolsite), [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleClientSite](/windows/desktop/api/oleidl/nn-oleidl-ioleclientsite), [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink), `IBoundObjectSite`, `INotifyDBEvents`, [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) Schnittstellen. Darüber hinaus wird die IDispatch-Schnittstelle (mit Unterstützung für die ambient-Eigenschaften und Ereignissenken) ebenfalls implementiert.

Um eine Website mit ActiveX-Steuerelement erstellen `COleControlSite`, leiten eine Klasse von `COleControlSite`. In Ihrer `CWnd`-abgeleitete Klasse für den Container (z. B. ein Dialogfenster) überschreiben die `CWnd::CreateControlSite` Funktion.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlSite`

## <a name="requirements"></a>Anforderungen

**Header:** afxocc.h

##  <a name="binddefaultproperty"></a>  COleControlSite::BindDefaultProperty

Bindet das aufrufende Objekt standardmäßige einfache gebundene Eigenschaft gemäß der Markierung in der Typbibliothek, auf den zugrunde liegenden Cursor, der durch die Datenquelle, Benutzername, Kennwort und SQL-Eigenschaften des Datenquellen Steuerelement definiert ist.

```
virtual void BindDefaultProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    LPCTSTR szFieldName,
    CWnd* pDSCWnd);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die DISPID einer Eigenschaft in einem datengebundenen Steuerelement, die an ein Datenquellen-Steuerelement gebunden werden soll.

*vtProp*<br/>
Gibt den Typ der Eigenschaft, die gebunden werden, z. B. VT_BSTR VT_VARIANT und So weiter.

*szFieldName*<br/>
Gibt den Namen der Spalte, in den Cursor, die von den Datenquellen-Steuerelement, an dem die Eigenschaft gebunden werden bereitgestellt.

*pDSCWnd*<br/>
Ein Zeiger auf die `CWnd`-abgeleitete Objekt, das Datenquellen Steuerelement hostet, die Eigenschaft gebunden werden wird.

### <a name="remarks"></a>Hinweise

Die `CWnd` Objekt auf dem Sie diese Funktion aufrufen, muss ein vom datengebundenen Steuerelement.

##  <a name="bindproperty"></a>  COleControlSite::BindProperty

Bindet das aufrufende Objekt einfache gebundene Eigenschaft gemäß der Markierung in der Typbibliothek, auf den zugrunde liegenden Cursor, der durch die Datenquelle, Benutzername, Kennwort und SQL-Eigenschaften des Datenquellen Steuerelement definiert ist.

```
virtual void BindProperty(
    DISPID dwDispId,
    CWnd* pWndDSC);
```

### <a name="parameters"></a>Parameter

*dwDispId*<br/>
Gibt die DISPID einer Eigenschaft in einem datengebundenen Steuerelement, die an ein Datenquellen-Steuerelement gebunden werden soll.

*pWndDSC*<br/>
Ein Zeiger auf die `CWnd`-abgeleitete Objekt, das Datenquellen Steuerelement hostet, die Eigenschaft gebunden werden wird.

### <a name="remarks"></a>Hinweise

Die `CWnd` Objekt auf dem Sie diese Funktion aufrufen, muss ein vom datengebundenen Steuerelement.

##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite

Erstellt ein neues `COleControlSite`-Objekt.

```
explicit COleControlSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Parameter

*pCtrlCont*<br/>
Ein Zeiger auf den Container des Steuerelements (womit das Fenster, das das Steuerelement AtiveX hostet).

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, indem die [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) Funktion. Weitere Informationen zum Anpassen von die Erstellung von Containern finden Sie unter [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite).

##  <a name="createcontrol"></a>  COleControlSite::CreateControl

Erstellt ein ActiveX-Steuerelement, von gehosteten der `COleControlSite` Objekt.

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
Ein Zeiger auf das Window-Objekt, das das Steuerelement darstellt.

*clsid*<br/>
Die eindeutige Klasse-ID des Steuerelements.

*lpszWindowName*<br/>
Ein Zeiger auf den Text im Steuerelement angezeigt werden. Legt den Wert der Eigenschaft für die Winodw die Beschriftung oder den Text fest, (sofern vorhanden).

*dwStyle*<br/>
Windows-Formate. Die verfügbaren Formate finden Sie unter den **"Hinweise"** Abschnitt.

*Rect*<br/>
Gibt an, die Größe und Position des Steuerelements. Es kann sein, entweder eine `CRect` Objekt oder ein `RECT` Struktur.

*nID*<br/>
Gibt an, der ID des Steuerelements untergeordnete Fenster

*pPersist*<br/>
Ein Zeiger auf eine `CFile` , die den dauerhaften Status für das Steuerelement enthält. Der Standardwert ist NULL, gibt an, dass das Steuerelement selbst ohne Wiederherstellung von seinen Zustand aus dem alle permanenten Speicher initialisiert. Wenn nicht NULL ist, wird ein Zeiger auf eine `CFile`-abgeleitetes Objekt, das persistente Daten des Steuerelements im Formular einen Stream oder ein Speicherkonto enthält. Diese Daten können in eine vorherige Aktivierung des Clients gespeichert wurden. Die `CFile` können weitere Daten enthalten, jedoch müssen der Lese-/ Schreibzugriff Zeiger auf das erste Byte von persistenten Daten festgelegt werden, zum Zeitpunkt des Aufrufs von `CreateControl`.

*bStorage*<br/>
Gibt an, ob die Daten in *pPersist* interpretiert werden soll, als `IStorage` oder `IStream` Daten. Wenn die Daten in *pPersist* ist ein Speicher, *bStorage* sollte "true" sein. Wenn die Daten in *pPersist* ist ein Datenstrom, *bStorage* sollte "false" sein. Der Standardwert ist "false".

*bstrLicKey*<br/>
Lizenz-Schlüsseldaten ist optional. Diese Daten ist nur für das Erstellen von Steuerelementen, die erfordern einen Laufzeit-Lizenzschlüssel erforderlich. Wenn das Steuerelement unterstützt die Lizenzierung, müssen Sie einen Lizenzschlüssel für die Erstellung des Steuerelements erfolgreich bereitstellen. Der Standardwert ist NULL.

*PPT*<br/>
Ein Zeiger auf eine `POINT` Struktur, die die linke obere Ecke des Steuerelements enthält. Die Größe des Steuerelements richtet sich nach dem Wert der *Psize*. Die *ppt* und *Psize* Werte sind eine optionale Methode, um die Größe und position Opf des Steuerelements.

*psize*<br/>
Ein Zeiger auf eine `SIZE` Struktur, die die Größe des Steuerelements enthält. Die linke obere Ecke richtet sich nach dem Wert der *ppt*. Die *ppt* und *Psize* Werte sind eine optionale Methode, um die Größe und position Opf des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Nur ein Teil der Windows *DwStyle* Flags werden von unterstützt `CreateControl`:

- WS_VISIBLE erstellt ein Fenster, das anfänglich sichtbar ist. Erforderlich, wenn das Steuerelement sofort wie gewöhnliche Fenster angezeigt werden soll.

- WS_DISABLED erstellt ein Fenster, das anfänglich deaktiviert ist. Ein deaktiviertes Fensters kann keine Eingabe vom Benutzer empfangen. Kann festgelegt werden, wenn das Steuerelement eine Enabled-Eigenschaft verfügt.

- WS_BORDER erstellt ein Fenster mit einem thin-Line-Rahmen. Kann festgelegt werden, wenn Steuerelement eine BorderStyle-Eigenschaft verfügt.

- WS_GROUP gibt das erste Steuerelement einer Gruppe von Steuerelementen an. Der Benutzer kann den Tastaturfokus von einem Steuerelement in der Gruppe zur nächsten ändern mithilfe der Richtung. Alle Steuerelemente, die mit dem WS_GROUP-Stil definiert wird, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit dem Stil WS_GROUP beendet die Gruppe und beginnt die nächste Gruppe.

- WS_TABSTOP gibt ein Steuerelement, das den Tastaturfokus erhalten kann, wenn der Benutzer die TAB-Taste drückt. Durch Drücken der TAB-Taste ändert den Tastaturfokus auf das nächste Steuerelement für den WS_TABSTOP-Stil.

Verwenden Sie die zweite Überladung, um die Standardgröße Steuerelemente zu erstellen.

##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl

Zerstört das `COleControlSite`-Objekt.

```
virtual BOOL DestroyControl();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Sobald Sie abgeschlossen ist, wird das Objekt aus dem Speicher freigegeben, und alle Zeiger auf das Objekt nicht mehr gültig sind.

##  <a name="doverb"></a>  COleControlSite::DoVerb

Führt das angegebene Verb aus.

```
virtual HRESULT DoVerb(
    LONG nVerb,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>Parameter

*nVerb*<br/>
Gibt das Verb ausgeführt. Sie können eine der folgenden enthalten:

|Wert|Bedeutung|Symbol|
|-----------|-------------|------------|
|0|Primäres Verb|OLEIVERB_PRIMARY|
|-1|Sekundäre verb|(Keine)|
|1|Zeigt das Objekt für die Bearbeitung.|OLEIVERB_SHOW|
|-2|Bearbeitet das Element in einem separaten Fenster.|OLEIVERB_OPEN|
|-3|Blendet das Objekt an.|OLEIVERB_HIDE|
|-4|Aktiviert eine direkte Kontrolle.|OLEIVERB_UIACTIVATE|
|-5|Aktiviert eine Steuerelement direkt ohne zusätzliche Elemente der Benutzeroberfläche.|OLEIVERB_INPLACEACTIVATE|
|-7|Anzeigen der Eigenschaften des Steuerelements an.|OLEIVERB_PROPERTIES|

*lpMsg*<br/>
Zeiger auf die Meldung, die das Element, das aktiviert werden, verursacht hat.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft direkt über des Steuerelements `IOleObject` Schnittstelle für das angegebene Verb aufzurufen. Wenn als Ergebnis dieses Funktionsaufrufs eine Ausnahme ausgelöst wird, wird ein HRESULT-Fehlercode zurückgegeben.

Weitere Informationen finden Sie unter [IOleObject](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) im Windows SDK.

##  <a name="enabledsc"></a>  COleControlSite::EnableDSC

Ermöglicht die Daten, die als Quelle für die Website des Steuerelements.

```
virtual void EnableDSC();
```

### <a name="remarks"></a>Hinweise

Wird aufgerufen, durch das Framework zu aktivieren und initialisieren Sie Daten, die als Quelle für die Website des Steuerelements. Überschreiben Sie diese Funktion, um benutzerdefiniertes Verhalten bereitstellen.

##  <a name="enablewindow"></a>  COleControlSite::EnableWindow

Aktiviert oder deaktiviert die Maus- und Tastatureingaben an die Website des Steuerelements.

```
virtual BOOL EnableWindow(BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
Gibt an, ob aktivieren oder deaktivieren das Fenster aus: "True", wenn im Fenster Eingaben werden soll, aktiviert ist, andernfalls "false".

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Fenster zuvor deaktiviert war, andernfalls 0.

##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents

Gibt an, ob die Website des Steuerelements behandeln oder ignorieren von Ereignissen von einem Steuerelement ausgelöst wird.

```
void FreezeEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Parameter

*bFreeze*<br/>
Gibt an, ob die Steuerelementsite das Akzeptieren von Ereignissen beenden möchte. Ungleich NULL, wenn das Steuerelement keine Ereignisse akzeptiert; andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Wenn *bFreeze* ist "true", die Website des Steuerelements fordert das Steuerelement zum Beenden der importieren Ereignisse. Wenn *bFreeze* ist "false", die Website des Steuerelements fordert das Steuerelement, um den Vorgang fortzusetzen, Auslösen von Ereignissen.

> [!NOTE]
>  Das Steuerelement ist nicht erforderlich, um das Auslösen von Ereignissen, gegebenenfalls durch die Website des Steuerelements zu beenden. Sie können das Ereignis weiterhin ausgelöst, aber alle nachfolgenden Ereignisse durch die Website des Steuerelements, ignoriert werden.

##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo

Ruft Informationen über die Tastatur mnemonische Zeichen und Tastaturverhalten eines Steuerelements ab.

```
void GetControlInfo();
```

### <a name="remarks"></a>Hinweise

Die Informationen werden gespeichert, [COleControlSite::m_ctlInfo](#m_ctlinfo).

##  <a name="getdefbtncode"></a>  COleControlSite::GetDefBtnCode

Bestimmt, ob das Steuerelement die Standardschaltfläche Push ist.

```
DWORD GetDefBtnCode();
```

### <a name="return-value"></a>Rückgabewert

Kann einer der folgenden Werte sein:

- DLGC_DEFPUSHBUTTON-Steuerelement ist die Standardschaltfläche im Dialogfeld.

- DLGC_UNDEFPUSHBUTTON-Steuerelement ist nicht als Standardschaltfläche im Dialogfeld.

- **0** Steuerelement ist keine Schaltfläche.

##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID

Ruft den Bezeichner des Steuerelements ab.

```
virtual int GetDlgCtrlID() const;
```

### <a name="return-value"></a>Rückgabewert

Der Dialogfeld-Elementbezeichner des Steuerelements.

##  <a name="geteventiid"></a>  COleControlSite::GetEventIID

Ruft einen Zeiger auf die Standard-Event-Schnittstelle des Steuerelements ab.

```
BOOL GetEventIID(IID* piid);
```

### <a name="parameters"></a>Parameter

*piid*<br/>
Ein Zeiger auf eine Schnittstellen-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich, andernfalls 0. Im Erfolgsfall *Piid* enthält die Schnittstellen-ID für die Standard-Event-Schnittstelle des Steuerelements.

##  <a name="getexstyle"></a>  COleControlSite::GetExStyle

Ruft die erweiterten Fensterstile ab.

```
virtual DWORD GetExStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Das Fenster des Steuerelements die Stile erweitert.

### <a name="remarks"></a>Hinweise

Rufen Sie zum Abrufen der regulären Stile [COleControlSite::GetStyle](#getstyle).

##  <a name="getproperty"></a>  COleControlSite::GetProperty

Ruft ab, der Eigenschaft des Steuerelements gemäß *DwDispID*.

```
virtual void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Dispatch-ID der Eigenschaft des Steuerelements finden `IDispatch` -Schnittstelle, abgerufen werden sollen.

*vtProp*<br/>
Gibt den Typ der Eigenschaft abgerufen werden sollen. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvProp*<br/>
Die Adresse der Variablen, die den Wert der Eigenschaft erhält. Es muss den vom angegebenen Typ übereinstimmen *VtProp*.

### <a name="remarks"></a>Hinweise

Der Wert wird zurückgegeben, über *PvProp*.

##  <a name="getstyle"></a>  COleControlSite::GetStyle

Ruft die Formatvorlagen der Site für das Steuerelement ab.

```
virtual DWORD GetStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Die Fensterstile.

### <a name="remarks"></a>Hinweise

Eine Liste der möglichen Werte, finden Sie unter [Windows Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Um die erweiterten Stile, der die Website des Steuerelements abzurufen, rufen [COleControlSite::GetExStyle](#getexstyle).

##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText

Ruft den aktuellen Text des Steuerelements ab.

```
virtual void GetWindowText(CString& str) const;
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf eine `CString` Objekt, das den aktuellen Text des Steuerelements enthält.

### <a name="remarks"></a>Hinweise

Wenn das Steuerelement die vordefinierte Caption-Eigenschaft unterstützt, wird dieser Wert zurückgegeben. Wenn die vordefinierte Caption-Eigenschaft nicht unterstützt wird, wird der Wert für die Text-Eigenschaft zurückgegeben.

##  <a name="invokehelper"></a>  COleControlSite::InvokeHelper

Ruft die Methode oder Eigenschaft, die anhand des *DwDispID*, in dem vom angegebenen Kontext *wFlags*.

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
Gibt die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` Schnittstelle, die aufgerufen werden.

*wFlags*<br/>
Flags, die den Kontext des Aufrufs von IDispatch:: Invoke beschreiben. Für eine mögliche *wFlags* Werte finden Sie unter `IDispatch::Invoke` im Windows SDK.

*vtRet*<br/>
Gibt den Typ des Rückgabewerts an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvRet*<br/>
Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Es muss den vom angegebenen Typ übereinstimmen *VtRet*.

*pbParamInfo*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge von Bytes, die den Objekttyp die folgenden Parameter angeben *PbParamInfo*. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Variable Parameterliste, der in der angegebenen Typen *PbParamInfo*.

### <a name="remarks"></a>Hinweise

Die *PbParamInfo* Parameter gibt die Typen der an die Methode oder Eigenschaft übergebenen Parameter. Die Variable Liste von Argumenten wird durch... in der Syntax-Deklaration dargestellt.

Diese Funktion konvertiert die Parameter auf VARIANTARG-Werte und ruft anschließend die `IDispatch::Invoke` Methode für das Steuerelement. Bei einem Fehler des Aufrufs von `IDispatch::Invoke` löst diese Funktion eine Ausnahme aus. Wenn der zurückgegebene Statuscode von `IDispatch::Invoke` ist `DISP_E_EXCEPTION`, diese Funktion löst eine `COleDispatchException` Objekt ist, andernfalls löst eine `COleException`.

##  <a name="invokehelperv"></a>  COleControlSite::InvokeHelperV

Ruft die Methode oder Eigenschaft, die anhand des *DwDispID*, in dem vom angegebenen Kontext *wFlags*.

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
Gibt die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` Schnittstelle, die aufgerufen werden.

*wFlags*<br/>
Flags, die den Kontext des Aufrufs von IDispatch:: Invoke beschreiben.

*vtRet*<br/>
Gibt den Typ des Rückgabewerts an. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvRet*<br/>
Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Es muss den vom angegebenen Typ übereinstimmen *VtRet*.

*pbParamInfo*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge von Bytes, die den Objekttyp die folgenden Parameter angeben *PbParamInfo*. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*argList*<br/>
Zeiger auf eine Variable Argumentliste.

### <a name="remarks"></a>Hinweise

Die *PbParamInfo* Parameter gibt die Typen der an die Methode oder Eigenschaft übergebenen Parameter. Zusätzliche Parameter für die Methode oder Eigenschaft, die aufgerufen wird, können mithilfe von übergeben werden die *Va_list* Parameter.

Diese Funktion wird in der Regel aufgerufen, indem `COleControlSite::InvokeHelper`.

##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton

Bestimmt, ob das Steuerelement die Standardschaltfläche ist.

```
BOOL IsDefaultButton();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Steuerelement die Standardschaltfläche für das Fenster, andernfalls NULL.

##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled

Bestimmt, ob die Website des Steuerelements aktiviert ist.

```
virtual BOOL IsWindowEnabled() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Steuerelement aktiviert ist, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Der Wert wird von der Eigenschaft des Steuerelements aktiviert abgerufen.

##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless

Bestimmt, ob das Objekt ein fensterloses Steuerelement ist.

```
BOOL m_bIsWindowless;
```

### <a name="remarks"></a>Hinweise

Ungleich NULL, wenn das Steuerelement kein Fenster besitzt, andernfalls NULL.

##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo

Informationen zum wie Tastatureingaben vom Steuerelement behandelt wird.

```
CONTROLINFO m_ctlInfo;
```

### <a name="remarks"></a>Hinweise

Diese Informationen werden gespeichert, einem [CONTROLINFO](/windows/desktop/api/ocidl/ns-ocidl-tagcontrolinfo) Struktur.

##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink

Enthält den Verbindungspunkt-Cookie aus der Ereignissenke des Steuerelements an.

```
DWORD m_dwEventSink;
```

##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus

Enthält verschiedene Informationen über das Steuerelement an.

```
DWORD m_dwMiscStatus;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc)im Windows SDK.

##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink

Enthält die [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) Cookie.

```
DWORD m_dwPropNotifySink;
```

##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle

Enthält die Stile im Fenster des Steuerelements an.

```
DWORD m_dwStyle;
```

##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd

Enthält das HWND des Steuerelements oder NULL, wenn das Steuerelement fensterlos sein.

```
HWND m_hWnd;
```

##  <a name="m_iidevents"></a>  COleControlSite::m_iidEvents

Enthält die Schnittstellen-ID des Steuerelements Standard Ereignissenken-Schnittstelle.

```
IID m_iidEvents;
```

##  <a name="m_nid"></a>  COleControlSite::m_nID

Des Steuerelements Dialogfeld-Element-ID enthält.

```
UINT m_nID;
```

##  <a name="m_pactiveobject"></a>  COleControlSite::m_pActiveObject

Enthält die [IOleInPlaceActiveObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceactiveobject) Schnittstelle des Steuerelements.

```
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;
```

##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont

Enthält der Container des Steuerelements (des Formulars darstellt).

```
COleControlContainer* m_pCtrlCont;
```

##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject

Enthält die `IOleInPlaceObject` [IOleInPlaceObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceobject) Schnittstelle des Steuerelements.

```
LPOLEINPLACEOBJECT m_pInPlaceObject;
```

##  <a name="m_pobject"></a>  COleControlSite::m_pObject

Enthält die `IOleObjectInterface` Schnittstelle des Steuerelements.

```
LPOLEOBJECT m_pObject;
```

##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject

Enthält die `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) Schnittstelle des Steuerelements.

```
IOleInPlaceObjectWindowless* m_pWindowlessObject;
```

##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl

Enthält einen Zeiger auf die `CWnd` -Objekt, das Steuerelement selbst darstellt.

```
CWnd* m_pWndCtrl;
```

##  <a name="m_rect"></a>  COleControlSite::m_rect

Enthält die Begrenzungen des Steuerelements relativ zum Fenster für den Container an.

```
CRect m_rect;
```

##  <a name="modifystyle"></a>  COleControlSite::ModifyStyle

Ändert die Formate des Steuerelements an.

```
virtual BOOL ModifyStyle(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

*dwRemove*<br/>
Die Formate aus der aktuellen Fensterstile entfernt werden soll.

*dwAdd*<br/>
Die Formate aus der aktuellen Window-Stile hinzugefügt werden.

*nFlags*<br/>
Fenster, die Positionierung von Flags. Eine Liste der möglichen Werte, finden Sie unter den [SetWindowPos](/windows/desktop/api/winuser/nf-winuser-setwindowpos) -Funktion in das Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Stile geändert werden, andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Des Steuerelements Stock Enabled-Eigenschaft wird die Einstellung für WS_DISABLED entsprechend geändert werden. Rahmenart Eigenschaft des Steuerelements wird entsprechend die angeforderte Einstellung für WS_BORDER geändert werden. Alle anderen Formate werden direkt auf das Fensterhandle des Steuerelements, angewendet werden, wenn ein solcher vorhanden ist.

Ändert das Window-Stile des Steuerelements an. Stile hinzugefügt oder entfernt werden soll, können mit dem bitweisen OR kombiniert werden ( &#124; ) Operator. Finden Sie unter den [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Funktion im Windows SDK für Informationen über die verfügbaren Fenster.

Wenn *nFlags* ungleich NULL ist, `ModifyStyle` wird die Win32-Funktion `SetWindowPos`, und das Fenster durch Kombinieren von zeichnet *nFlags* mit den vier folgenden Flags:

- SWP_NOSIZE behält die aktuelle Größe.

- SWP_NOMOVE behält die aktuelle Position.

- SWP_NOZORDER behält den aktuelle Z-Reihenfolge.

- SWP_NOACTIVATE werden diese nicht das Fenster aktiviert.

So ändern Sie ein Fenster des Erweiterte Stile, rufen Sie [ModifyStyleEx](#modifystyleex).

##  <a name="modifystyleex"></a>  COleControlSite::ModifyStyleEx

Ändert die erweiterten Stile des Steuerelements an.

```
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

*dwRemove*<br/>
Die erweiterten Stile aus der aktuellen Fensterstile entfernt werden soll.

*dwAdd*<br/>
Die erweiterten Stile aus der aktuellen Window-Stile hinzugefügt werden.

*nFlags*<br/>
Fenster, die Positionierung von Flags. Eine Liste der möglichen Werte, finden Sie unter den [SetWindowPos](/windows/desktop/api/winuser/nf-winuser-setwindowpos) -Funktion in das Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Stile geändert werden, andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Des Steuerelements Stock Appearance-Eigenschaft wird die Einstellung für WS_EX_CLIENTEDGE entsprechend geändert werden. Alle anderen erweiterten Fensterstile werden direkt auf das Fensterhandle des Steuerelements, angewendet, wenn ein solcher vorhanden ist.

Ändert das Fenster Erweiterte Stile des Website-Steuerelements. Stile hinzugefügt oder entfernt werden soll, können mit dem bitweisen OR kombiniert werden ( &#124; ) Operator. Finden Sie unter den [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Funktion im Windows SDK für Informationen über die verfügbaren Fenster.

Wenn *nFlags* ungleich NULL ist, `ModifyStyleEx` wird die Win32-Funktion `SetWindowPos`, und das Fenster durch Kombinieren von zeichnet *nFlags* mit den vier folgenden Flags:

- SWP_NOSIZE behält die aktuelle Größe.

- SWP_NOMOVE behält die aktuelle Position.

- SWP_NOZORDER behält den aktuelle Z-Reihenfolge.

- SWP_NOACTIVATE werden diese nicht das Fenster aktiviert.

So ändern Sie ein Fenster des Erweiterte Stile, rufen Sie [ModifyStyle](#modifystyle).

##  <a name="movewindow"></a>  COleControlSite::MoveWindow

Ändert die Position des Steuerelements.

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
Die neue Position des oberen Rand des Fensters.

*nWidth*<br/>
Die neue Breite des Fensters

*nHeight*<br/>
Die neue Höhe des Fensters.

##  <a name="quickactivate"></a>  COleControlSite::QuickActivate

Schnelle aktiviert das enthaltene Steuerelement.

```
virtual BOOL QuickActivate();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Website des Steuerelements aktiviert wurde, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte aufgerufen werden, nur dann, wenn der Benutzer des Erstellungsprozesses des Steuerelements außer Kraft gesetzt wird.

Die `IPersist*::Load` und `IPersist*::InitNew` Methoden sollte aufgerufen werden, nachdem die schnelle Aktivierung stattfindet. Das Steuerelement sollte dessen Verbindungen mit des Containers senken während der Aktivierung der schnellen herstellen. Diese Verbindungen sind jedoch nicht live bis `IPersist*::Load` oder `IPersist*::InitNew` aufgerufen wurde.

##  <a name="safesetproperty"></a>  COleControlSite::SafeSetProperty

Legt die Steuerelementeigenschaft, die anhand des *DwDispID*.

```
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` -Schnittstelle, festgelegt werden.

*vtProp*<br/>
Gibt den Typ der Eigenschaft festgelegt werden. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Einen einzelnen Parameter des Typs vom angegebenen *VtProp*.

### <a name="return-value"></a>Rückgabewert

Ungleich 0, wenn erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Im Gegensatz zu `SetProperty` und `SetPropertyV`, wenn ein Fehler auftritt (z. B. versuchen, eine nicht vorhandene Eigenschaft festlegen), wird keine Ausnahme ausgelöst.

##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton

Legt das Steuerelement als Standardschaltfläche an.

```
void SetDefaultButton(BOOL bDefault);
```

### <a name="parameters"></a>Parameter

*bStandardstufe*<br/>
Ungleich NULL, wenn das Steuerelement die Standardschaltfläche werden soll; andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Das Steuerelement muss OLEMISC_ACTSLIKEBUTTON Status-bit-Satz verfügen.

##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID

Ändert den Wert der Dialogfeld-Element-ID des Steuerelements.

```
virtual int SetDlgCtrlID(int nID);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Der neue Bezeichnerwert.

### <a name="return-value"></a>Rückgabewert

Im Erfolgsfall Element im vorherige Dialogfeld Bezeichner des Fensters; andernfalls 0.

### <a name="remarks"></a>Hinweise

##  <a name="setfocus"></a>  COleControlSite::SetFocus

Legt den Fokus auf das Steuerelement.

```
virtual CWnd* SetFocus();
virtual CWnd* SetFocus(LPMSG lpmsg);
```

### <a name="parameters"></a>Parameter

*lpmsg*<br/>
Ein Zeiger auf eine [MSG-Struktur](/windows/desktop/api/winuser/ns-winuser-tagmsg). Diese Struktur enthält das Windows-Meldung Auslösen der `SetFocus` Anforderung für das Steuerelement, das in die Website des aktuellen Steuerelements enthalten sind.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Fenster, das zuvor den Fokus hatte.

##  <a name="setproperty"></a>  COleControlSite::SetProperty

Legt die Steuerelementeigenschaft, die anhand des *DwDispID*.

```
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` -Schnittstelle, festgelegt werden.

*vtProp*<br/>
Gibt den Typ der Eigenschaft festgelegt werden. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Einen einzelnen Parameter des Typs vom angegebenen *VtProp*.

### <a name="remarks"></a>Hinweise

Wenn `SetProperty` einen Fehler erkennt, wird eine Ausnahme ausgelöst.

Der Typ der Ausnahme wird durch den Rückgabewert des Versuchs, legen Sie die Eigenschaft oder Methode bestimmt. Wenn der Rückgabewert ist `DISP_E_EXCEPTION`, `COleDispatchExcpetion` ausgelöst wird; andernfalls ein `COleException`.

##  <a name="setpropertyv"></a>  COleControlSite::SetPropertyV

Legt die Steuerelementeigenschaft, die anhand des *DwDispID*.

```
virtual void SetPropertyV(
    DISPID dwDispID,
    VARTYPE vtProp,
    va_list argList);
```

### <a name="parameters"></a>Parameter

*dwDispID*<br/>
Gibt die Dispatch-ID der Eigenschaft oder Methode, finden Sie auf des Steuerelements `IDispatch` -Schnittstelle, festgelegt werden.

*vtProp*<br/>
Gibt den Typ der Eigenschaft festgelegt werden. Informationen zu den möglichen Werten finden Sie im Abschnitt „Anmerkungen“ für [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*argList*<br/>
Zeiger auf die Liste der Argumente.

### <a name="remarks"></a>Hinweise

Zusätzliche Parameter für die Methode oder Eigenschaft, die aufgerufen wird, können Passeed werden mithilfe der *Arg_list* Parameter. Wenn `SetProperty` einen Fehler erkennt, wird eine Ausnahme ausgelöst.

Der Typ der Ausnahme wird durch den Rückgabewert des Versuchs, legen Sie die Eigenschaft oder Methode bestimmt. Wenn der Rückgabewert ist `DISP_E_EXCEPTION`, `COleDispatchExcpetion` ausgelöst wird; andernfalls ein `COleException`.

##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos

Legt fest, die Größe, Position und Z-Reihenfolge von der Website des Steuerelements.

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
Die neue Position des oberen Rand des Fensters.

*CX*<br/>
Die neue Breite des Fensters

*CY*<br/>
Die neue Höhe des Fensters.

*nFlags*<br/>
Gibt an, das Fenster größenanpassung und Positionierung von Flags. Mögliche Werte finden Sie im Abschnitt "Hinweise" für [SetWindowPos](/windows/desktop/api/winuser/nf-winuser-setwindowpos) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich, andernfalls NULL.

##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText

Legt den Text für die Website des Steuerelements fest.

```
virtual void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*lpszString*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge als den neuen Text für Titel oder Steuerelement verwendet werden soll.

### <a name="remarks"></a>Hinweise

Diese Funktion versucht zunächst, legen Sie die vordefinierte Caption-Eigenschaft verwendet werden. Wenn die vordefinierte Caption-Eigenschaft nicht unterstützt wird, wird stattdessen die Text-Eigenschaft festgelegt.

##  <a name="showwindow"></a>  COleControlSite::ShowWindow

Legt die Show Zustand des Fensters fest.

```
virtual BOOL ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Parameter

*nCmdShow*<br/>
Gibt an, wie die Website des Steuerelements angezeigt werden. Es muss eine der folgenden Werte sein:

- SW_HIDE Blendet das Fenster aus und übergibt die Aktivierung in ein anderes Fenster.

- SW_MINIMIZE minimiert das Fenster, und die Fenster das obersten Ebene in der Liste der aktiviert.

- SW_RESTORE aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert ist, wird Sie von Windows an seiner ursprünglichen Größe und Position wiederhergestellt.

- SW_SHOW aktiviert das Fenster und zeigt es in seiner aktuellen Größe und Position.

- "Sw_showmaximized" aktiviert das Fenster und zeigt ihn als ein maximiertes Fenster.

- SW_SHOWMINIMIZED aktiviert das Fenster und wird als Symbol angezeigt.

- SW_SHOWMINNOACTIVE zeigt das Fenster als Symbol. Die derzeit aktive Fenster bleibt aktiv.

- SW_SHOWNA zeigt das Fenster im aktuellen Zustand. Die derzeit aktive Fenster bleibt aktiv.

- SW_SHOWNOACTIVATE zeigt das Fenster, in der letzten Größe und Position. Die derzeit aktive Fenster bleibt aktiv.

- Entweder "SW_SHOWNORMAL" aktiviert und zeigt das Fenster an. Wenn das Fenster minimiert oder maximiert ist, wird Sie von Windows an seiner ursprünglichen Größe und Position wiederhergestellt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Fenster bereits sichtbar war; 0, wenn das Fenster bereits ausgeblendet wurde.

## <a name="see-also"></a>Siehe auch

[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleControlContainer-Klasse](../../mfc/reference/colecontrolcontainer-class.md)
