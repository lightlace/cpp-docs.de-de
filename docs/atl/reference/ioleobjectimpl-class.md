---
title: IOleObjectImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
ms.openlocfilehash: c228d5030c3577af22feda6a0d03769867b1c5c3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268459"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl-Klasse

Diese Klasse implementiert `IUnknown` und ist die Dienstprinzipale-Schnittstelle über die ein Container, die mit einem Steuerelement kommuniziert.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IOleObjectImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IOleObjectImpl::Advise](#advise)|Richtet eine Advise-Verbindung mit dem Steuerelement.|
|[IOleObjectImpl::Close](#close)|Ändert den Zustand des Steuerelements ausgeführt geladen.|
|[IOleObjectImpl::DoVerb](#doverb)|Weist das Steuerelement an eine der aufgelisteten Aktionen ausführen.|
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Weist das Steuerelement in einem beliebigen Zustand rückgängig zu verwerfen, den er verwaltet.|
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Weist das Steuerelement die Benutzeroberfläche aus Ansicht entfernen.|
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Führt das Steuerelement und installiert das Fenster, jedoch wird die Benutzeroberfläche des Steuerelements nicht installiert.|
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Bewirkt, dass das Steuerelement bearbeitet werden, öffnen Sie in einem separaten Fenster geöffnet werden.|
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|Führt die angegebene Aktion aus, wenn der Benutzer das Steuerelement doppelklickt. Das Steuerelement definiert die Aktion, in der Regel, um das Steuerelement direkt zu aktivieren.|
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Zeigt eine neu eingefügte-Steuerelement für dem Benutzer an.|
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Aktiviert das Steuerelement direkt, und zeigt die Benutzeroberfläche des Steuerelements, z. B. Menüs und Symbolleisten.|
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Listet die Advise-Verbindungen des Steuerelements.|
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Listet die Aktionen für das Steuerelement.|
|[IOleObjectImpl::GetClientSite](#getclientsite)|Ruft die Clientsite des Steuerelements ab.|
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Ruft Daten aus der Zwischenablage ab. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::GetExtent](#getextent)|Ruft das Ausmaß der Anzeigebereich des Steuerelements ab.|
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Ruft den Status des Steuerelements ab.|
|[IOleObjectImpl::GetMoniker](#getmoniker)|Ruft das Steuerelement den Moniker ab. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Ruft die Klassenbezeichner des Steuerelements ab.|
|[IOleObjectImpl::GetUserType](#getusertype)|Ruft den Namen des Steuerelements Benutzertyp ab.|
|[IOleObjectImpl::InitFromData](#initfromdata)|Initialisiert das Steuerelement aus der ausgewählten Daten. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Überprüft, ob das Steuerelement auf dem neuesten Stand ist. Es gibt S_OK zurück, die ATL-Implementierung.|
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Wird aufgerufen, indem [DoVerbDiscardUndo](#doverbdiscardundo) nach, wieder rückgängig zu machen verworfen wird.|
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Wird aufgerufen, indem [DoVerbHide](#doverbhide) nach dem das Steuerelement ausgeblendet ist.|
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Wird aufgerufen, indem [DoVerbInPlaceActivate](#doverbinplaceactivate) nach dem das Steuerelement direkt aktiviert ist.|
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Wird aufgerufen, indem [DoVerbOpen](#doverbopen) nachdem das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.|
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Wird aufgerufen, indem [DoVerbShow](#doverbshow) nach dem das Steuerelement sichtbar gemacht wurde.|
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Wird aufgerufen, indem [DoVerbUIActivate](#doverbuiactivate) nach der Aktivierung der Benutzeroberfläche des Steuerelements.|
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Wird aufgerufen, indem [DoVerbDiscardUndo](#doverbdiscardundo) vor dem das Rückgängigmachen der Zustand wird verworfen.|
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Wird aufgerufen, indem [DoVerbHide](#doverbhide) , bevor das Steuerelement ausgeblendet ist.|
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Wird aufgerufen, indem [DoVerbInPlaceActivate](#doverbinplaceactivate) , bevor das Steuerelement direkt aktiviert ist.|
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Wird aufgerufen, indem [DoVerbOpen](#doverbopen) , bevor das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.|
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Wird aufgerufen, indem [DoVerbShow](#doverbshow) , bevor das Steuerelement sichtbar gemacht wurde.|
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Wird aufgerufen, indem [DoVerbUIActivate](#doverbuiactivate) vor der Benutzeroberfläche des Steuerelements aktiviert wurde.|
|[IOleObjectImpl::SetClientSite](#setclientsite)|Teilt dem Steuerelement über die Client-Website im Container.|
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Empfiehlt ein Farbschema des Steuerelements-Anwendung, sofern vorhanden. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::SetExtent](#setextent)|Legt den Umfang der Anzeigebereich des Steuerelements fest.|
|[IOleObjectImpl::SetHostNames](#sethostnames)|Teilt dem Steuerelement die Namen der Anwendung mit Containern und Containerdokument an.|
|[IOleObjectImpl::SetMoniker](#setmoniker)|Teilt dem Steuerelement was des Monikers ist. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IOleObjectImpl::Unadvise](#unadvise)|Löscht eine Advise-Verbindung mit dem Steuerelement.|
|[IOleObjectImpl::Update](#update)|Aktualisiert das Steuerelement an. Es gibt S_OK zurück, die ATL-Implementierung.|

## <a name="remarks"></a>Hinweise

Die [IOleObject](/windows/desktop/api/oleidl/nn-oleidl-ioleobject) Schnittstelle ist der Prinzipal über die ein Container, die mit einem Steuerelement kommuniziert. Klasse `IOleObjectImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="advise"></a>  IOleObjectImpl::Advise

Richtet eine Advise-Verbindung mit dem Steuerelement.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::Advise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-advise) in das Windows SDK.

##  <a name="close"></a>  IOleObjectImpl::Close

Ändert den Zustand des Steuerelements ausgeführt geladen.

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>Hinweise

Das Steuerelement deaktiviert, und zerstört das Fenster des Steuerelements, wenn es vorhanden ist. Wenn das Steuerelement Datenmember Klasse [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) ist "true" und die *DwSaveOption* Parameter entweder OLECLOSE_SAVEIFDIRTY oder OLECLOSE_PROMPTSAVE, werden die Eigenschaften des Steuerelements vor dem Schließen gespeichert.

Die Zeiger frei, die in die Steuerelement-Klassendatenmember [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) und [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) freigegeben werden, und die Datenelemente [CComControlBase:: M_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), und [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) auf "false" festgelegt sind.

Finden Sie unter [IOleObject::Close](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-close) in das Windows SDK.

##  <a name="doverb"></a>  IOleObjectImpl::DoVerb

Weist das Steuerelement an eine der aufgelisteten Aktionen ausführen.

```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```

### <a name="remarks"></a>Hinweise

Abhängig vom Wert `iVerb`, eines der ATL `DoVerb` Hilfsfunktionen wie folgt aufgerufen wird:

|*iVerb* Wert|DoVerb-Hilfsfunktion aufgerufen|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[DoVerbInPlaceActivate](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|
|OLEIVERB_UIACTIVATE|[DoVerbUIActivate](#doverbuiactivate)|

Finden Sie unter [IOleObject](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) in das Windows SDK.

##  <a name="doverbdiscardundo"></a>  IOleObjectImpl::DoVerbDiscardUndo

Weist das Steuerelement in einem beliebigen Zustand rückgängig zu verwerfen, den er verwaltet.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
[in] Zeiger auf das Rechteck des Containers möchte das Steuerelement in gezeichnet.

*hwndParent*<br/>
[in] Handle des Fensters, das das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="doverbhide"></a>  IOleObjectImpl::DoVerbHide

Deaktiviert und entfernt das Steuerelement der Benutzeroberfläche und blendet das Steuerelement.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
[in] Zeiger auf das Rechteck des Containers möchte das Steuerelement in gezeichnet.

*hwndParent*<br/>
[in] Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="doverbinplaceactivate"></a>  IOleObjectImpl::DoVerbInPlaceActivate

Führt das Steuerelement und installiert das Fenster, jedoch wird die Benutzeroberfläche des Steuerelements nicht installiert.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
[in] Zeiger auf das Rechteck des Containers möchte das Steuerelement in gezeichnet.

*hwndParent*<br/>
[in] Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Aktiviert die Kontrolle durch den Aufruf [CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Es sei denn, die Control-Klasse-Datenmember `m_bWindowOnly` ist "true", `DoVerbInPlaceActivate` zunächst versucht, auf das Steuerelement als fensterloses Steuerelement aktivieren (möglich, nur dann, wenn der Container unterstützt [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless)). Wenn dies fehlschlägt, wird die Funktion versucht, auf das Steuerelement mit erweiterten Features aktivieren (möglich, nur dann, wenn der Container unterstützt [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex)). Wenn dies fehlschlägt, wird die Funktion versucht, das Steuerelement keine erweiterten Features aktivieren (möglich, nur dann, wenn der Container unterstützt [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite)). Wenn die Aktivierung erfolgreich ist, benachrichtigt die Funktion den Container, dass das Steuerelement aktiviert wurde.

##  <a name="doverbopen"></a>  IOleObjectImpl::DoVerbOpen

Bewirkt, dass das Steuerelement bearbeitet werden, öffnen Sie in einem separaten Fenster geöffnet werden.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
[in] Zeiger auf das Rechteck des Containers möchte das Steuerelement in gezeichnet.

*hwndParent*<br/>
[in] Handle des Fensters, das das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="doverbprimary"></a>  IOleObjectImpl::DoVerbPrimary

Definiert die Aktion ausgeführt, wenn der Benutzer das Steuerelement doppelklickt.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
[in] Zeiger auf das Rechteck des Containers möchte das Steuerelement in gezeichnet.

*hwndParent*<br/>
[in] Handle des Fensters, das das Steuerelement enthält.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Legen Sie in der Standardeinstellung auf die Eigenschaftenseiten angezeigt. Sie können dies in der Steuerelementklasse aufzurufende auf Doppelklicken Sie auf ein anderes Verhalten überschreiben. z. B. spielen Sie ein Video ab, oder wechseln Sie direkt aktiv.

##  <a name="doverbshow"></a>  IOleObjectImpl::DoVerbShow

Gibt den Container aus, um das Steuerelement sichtbar zu machen.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
[in] Zeiger auf das Rechteck des Containers möchte das Steuerelement in gezeichnet.

*hwndParent*<br/>
[in] Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="doverbuiactivate"></a>  IOleObjectImpl::DoVerbUIActivate

Aktiviert die Benutzeroberfläche des Steuerelements aus, und benachrichtigt den Container, dass die Menüs von zusammengesetzten Menüs ersetzt werden.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parameter

*prcPosRec*<br/>
[in] Zeiger auf das Rechteck des Containers möchte das Steuerelement in gezeichnet.

*hwndParent*<br/>
[in] Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

##  <a name="enumadvise"></a>  IOleObjectImpl::EnumAdvise

Stellt eine Enumeration von registrierten Advise-Verbindungen für dieses Steuerelement an.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::EnumAdvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumadvise) in das Windows SDK.

##  <a name="enumverbs"></a>  IOleObjectImpl::EnumVerbs

Stellt eine Enumeration registrierter Aktionen (Verben) für dieses Steuerelement durch Aufrufen von `OleRegEnumVerbs`.

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>Hinweise

Sie können RGS-Datei Ihres Projekts Verben hinzufügen. Sehen Sie z. B. CIRCCTL. RGS konnte nicht in der [CIRC](../../visual-cpp-samples.md) Beispiel.

Finden Sie unter [IOleObject:: EnumVerbs](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumverbs) in das Windows SDK.

##  <a name="getclientsite"></a>  IOleObjectImpl::GetClientSite

Setzt den Mauszeiger in die Steuerelement-Klassendatenmember [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) in *PpClientSite* und inkrementiert den Verweiszähler für den Zeiger.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::GetClientSite](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getclientsite) in das Windows SDK.

##  <a name="getclipboarddata"></a>  IOleObjectImpl::GetClipboardData

Ruft Daten aus der Zwischenablage ab.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::GetClipboardData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) in das Windows SDK.

##  <a name="getextent"></a>  IOleObjectImpl::GetExtent

Ruft die Größe des Steuerelements auf einer ausgeführten in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) ab.

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Hinweise

Die Größe wird gespeichert, in der Steuerelement-Klassendatenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).

Finden Sie unter [IOleObject::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getextent) in das Windows SDK.

##  <a name="getmiscstatus"></a>  IOleObjectImpl::GetMiscStatus

Gibt einen Zeiger auf registrierte Statusinformationen für das Steuerelement durch Aufrufen von `OleRegGetMiscStatus`.

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>Hinweise

Die Statusinformationen handelt es sich um Verhaltensweisen, die von den Daten des Steuerelements und die Darstellung unterstützt. Sie können Statusinformationen RGS-Datei Ihres Projekts hinzufügen.

Finden Sie unter [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) in das Windows SDK.

##  <a name="getmoniker"></a>  IOleObjectImpl::GetMoniker

Ruft das Steuerelement den Moniker ab.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::GetMoniker](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmoniker) in das Windows SDK.

##  <a name="getuserclassid"></a>  IOleObjectImpl::GetUserClassID

Gibt die Klassenbezeichner des Steuerelements zurück.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::GetUserClassID](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getuserclassid) in das Windows SDK.

##  <a name="getusertype"></a>  IOleObjectImpl::GetUserType

Gibt den Namen des Steuerelements Benutzertyp durch Aufrufen von `OleRegGetUserType`.

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>Hinweise

Der Benutzertyp-Name ist für die Anzeige in Benutzeroberflächen-Elemente wie Menüs und Dialogfelder verwendet. Sie können die Benutzer-Typnamen in der RGS-Datei des Projekts ändern.

Finden Sie unter [IOleObject::GetUserType](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getusertype) in das Windows SDK.

##  <a name="initfromdata"></a>  IOleObjectImpl::InitFromData

Initialisiert das Steuerelement aus der ausgewählten Daten.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [InitFromData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-initfromdata) in das Windows SDK.

##  <a name="isuptodate"></a>  IOleObjectImpl::IsUpToDate

Überprüft, ob das Steuerelement auf dem neuesten Stand ist.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::IsUpToDate](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-isuptodate) in das Windows SDK.

##  <a name="onpostverbdiscardundo"></a>  IOleObjectImpl::OnPostVerbDiscardUndo

Wird aufgerufen, indem [DoVerbDiscardUndo](#doverbdiscardundo) nach, wieder rückgängig zu machen verworfen wird.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit der gewünschten Code ausgeführt, nachdem, wieder rückgängig zu machen verworfen wird.

##  <a name="onpostverbhide"></a>  IOleObjectImpl::OnPostVerbHide

Wird aufgerufen, indem [DoVerbHide](#doverbhide) nach dem das Steuerelement ausgeblendet ist.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit der gewünschten Code ausgeführt, nachdem das Steuerelement ausgeblendet ist.

##  <a name="onpostverbinplaceactivate"></a>  IOleObjectImpl::OnPostVerbInPlaceActivate

Wird aufgerufen, indem [DoVerbInPlaceActivate](#doverbinplaceactivate) nach dem das Steuerelement direkt aktiviert ist.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit der gewünschten Code ausgeführt, nachdem das Steuerelement direkt aktiviert ist.

##  <a name="onpostverbopen"></a>  IOleObjectImpl::OnPostVerbOpen

Wird aufgerufen, indem [DoVerbOpen](#doverbopen) nachdem das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit zu bearbeitenden ausgeführt, nachdem das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.

##  <a name="onpostverbshow"></a>  IOleObjectImpl::OnPostVerbShow

Wird aufgerufen, indem [DoVerbShow](#doverbshow) nach dem das Steuerelement sichtbar gemacht wurde.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit zu bearbeitenden ausgeführt, nachdem das Steuerelement sichtbar gemacht wurde.

##  <a name="onpostverbuiactivate"></a>  IOleObjectImpl::OnPostVerbUIActivate

Wird aufgerufen, indem [DoVerbUIActivate](#doverbuiactivate) nach der Aktivierung der Benutzeroberfläche des Steuerelements.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode mit Code, der ausgeführt wird, nach der Aktivierung der Benutzeroberfläche des Steuerelements enthalten sein sollen.

##  <a name="onpreverbdiscardundo"></a>  IOleObjectImpl::OnPreVerbDiscardUndo

Wird aufgerufen, indem [DoVerbDiscardUndo](#doverbdiscardundo) vor dem das Rückgängigmachen der Zustand wird verworfen.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass wieder rückgängig zu machen, die verworfen wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.

##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide

Wird aufgerufen, indem [DoVerbHide](#doverbhide) , bevor das Steuerelement ausgeblendet ist.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement ausgeblendet, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.

##  <a name="onpreverbinplaceactivate"></a>  IOleObjectImpl::OnPreVerbInPlaceActivate

Wird aufgerufen, indem [DoVerbInPlaceActivate](#doverbinplaceactivate) , bevor das Steuerelement direkt aktiviert ist.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement aktiviert wird, vorhanden, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.

##  <a name="onpreverbopen"></a>  IOleObjectImpl::OnPreVerbOpen

Wird aufgerufen, indem [DoVerbOpen](#doverbopen) , bevor das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.

##  <a name="onpreverbshow"></a>  IOleObjectImpl::OnPreVerbShow

Wird aufgerufen, indem [DoVerbShow](#doverbshow) , bevor das Steuerelement sichtbar gemacht wurde.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement sichtbar gemacht wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.

##  <a name="onpreverbuiactivate"></a>  IOleObjectImpl::OnPreVerbUIActivate

Wird aufgerufen, indem [DoVerbUIActivate](#doverbuiactivate) vor der Benutzeroberfläche des Steuerelements aktiviert wurde.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Um zu verhindern, dass das Steuerelement der Benutzeroberfläche aktiviert wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.

##  <a name="setclientsite"></a>  IOleObjectImpl::SetClientSite

Teilt dem Steuerelement über die Client-Website im Container.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>Hinweise

Die Methode gibt S_OK zurück.

Finden Sie unter [IOleObject:: SetClientSite](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setclientsite) in das Windows SDK.

##  <a name="setcolorscheme"></a>  IOleObjectImpl::SetColorScheme

Empfiehlt ein Farbschema des Steuerelements-Anwendung, sofern vorhanden.

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) in das Windows SDK.

##  <a name="setextent"></a>  IOleObjectImpl::SetExtent

Legt den Umfang der Anzeigebereich des Steuerelements fest.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Hinweise

Andernfalls `SetExtent` speichert den Wert verweist `psizel` in der Steuerelement-Klassendatenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Dieser Wert ist in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit).

Wenn das Steuerelement Datenmember Klasse [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) ist "true", `SetExtent` speichert zudem den Wert verweist `psizel` in der Steuerelement-Klassendatenmember [CComControlBase::m_sizeNatural ](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).

Wenn das Steuerelement Datenmember Klasse [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) ist "true", `SetExtent` Aufrufe `SendOnDataChange` und `SendOnViewChange` benachrichtigt alle Advise-Senken der Advise-Inhaber, die die Größe des Steuerelements wurde registriert geändert.

Finden Sie unter [IOleObject:: SetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setextent) in das Windows SDK.

##  <a name="sethostnames"></a>  IOleObjectImpl::SetHostNames

Teilt dem Steuerelement die Namen der Anwendung mit Containern und Containerdokument an.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::SetHostNames](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-sethostnames) in das Windows SDK.

##  <a name="setmoniker"></a>  IOleObjectImpl::SetMoniker

Teilt dem Steuerelement was des Monikers ist.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::SetMoniker](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setmoniker) in das Windows SDK.

##  <a name="unadvise"></a>  IOleObjectImpl::Unadvise

Löscht die Advise-Verbindung gespeichert, in der Steuerelementklasse `m_spOleAdviseHolder` -Datenmember.

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::Unadvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-unadvise) in das Windows SDK.

##  <a name="update"></a>  IOleObjectImpl::Update

Aktualisiert das Steuerelement an.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IOleObject::Update](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-update) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX-Steuerelemente Schnittstellen](/windows/desktop/com/activex-controls-interfaces)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
