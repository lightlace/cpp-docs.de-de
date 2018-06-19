---
title: IOleObjectImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a98d3e0ad75d2eaa0325699369bfe4473182049
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366194"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl-Klasse
Diese Klasse implementiert **IUnknown** und ist die principal Schnittstelle, über die ein Container, die mit einem Steuerelement kommuniziert.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IOleObjectImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](#advise)|Richtet eine Advise-Verbindung mit dem Steuerelement.|  
|[IOleObjectImpl::Close](#close)|Ändert sich der Zustand des Steuerelements von ausgeführt geladen.|  
|[IOleObjectImpl::DoVerb](#doverb)|Weist das Steuerelement an eine der aufgelisteten Aktionen ausführen.|  
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Weist das Steuerelement in einem beliebigen Zustand rückgängig zu verwerfen, den sie verwalten.|  
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Weist das Steuerelement die Benutzeroberfläche aus der Ansicht entfernen.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Führt das Steuerelement und das Fenster installiert, aber das Steuerelement-Benutzeroberfläche wird nicht installiert.|  
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Bewirkt, dass das Steuerelement bearbeitet werden, öffnen Sie in einem separaten Fenster angezeigt werden.|  
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|Führt die angegebene Aktion aus, wenn der Benutzer das Steuerelement doppelklickt. Das Steuerelement definiert die Aktion, in der Regel um das Steuerelement direkt zu aktivieren.|  
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Zeigt eine neu eingefügte-Steuerelement für dem Benutzer an.|  
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Aktiviert das Steuerelement platzieren, und zeigt das Steuerelement-Benutzeroberfläche, z. B. Menüs und Symbolleisten.|  
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Listet die Advise-Verbindungen des Steuerelements.|  
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Listet die Aktionen für das Steuerelement.|  
|[IOleObjectImpl::GetClientSite](#getclientsite)|Ruft das Steuerelement Clientstandort ab.|  
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Ruft Daten aus der Zwischenablage ab. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleObjectImpl::GetExtent](#getextent)|Ruft den Umfang der Anzeigebereich des Steuerelements ab.|  
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Ruft den Status des Steuerelements ab.|  
|[IOleObjectImpl::GetMoniker](#getmoniker)|Ruft das Steuerelement-Moniker ab. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Ruft die Klassen-ID des Steuerelements ab.|  
|[IOleObjectImpl::GetUserType](#getusertype)|Ruft die Benutzertyp Namen des Steuerelements ab.|  
|[IOleObjectImpl::InitFromData](#initfromdata)|Initialisiert das Steuerelement aus der ausgewählten Daten. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Überprüft, ob das Steuerelement auf dem neuesten Stand ist. Gibt die ATL-Implementierung `S_OK`.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Wird aufgerufen, indem [DoVerbDiscardUndo](#doverbdiscardundo) nach, dass Sie wieder rückgängig zu machen verworfen wird.|  
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Wird aufgerufen, indem [DoVerbHide](#doverbhide) nachdem das Steuerelement ausgeblendet ist.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Wird aufgerufen, indem [DoVerbInPlaceActivate](#doverbinplaceactivate) nachdem das Steuerelement direkt aktiviert ist.|  
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Wird aufgerufen, indem [DoVerbOpen](#doverbopen) nachdem das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wurde.|  
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Wird aufgerufen, indem [DoVerbShow](#doverbshow) nachdem das Steuerelement sichtbar gemacht wurde.|  
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Wird aufgerufen, indem [DoVerbUIActivate](#doverbuiactivate) nach der Aktivierung der Benutzeroberfläche des Steuerelements.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Wird aufgerufen, indem [DoVerbDiscardUndo](#doverbdiscardundo) vor der Rückgängig Status verworfen wird.|  
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Wird aufgerufen, indem [DoVerbHide](#doverbhide) , bevor das Steuerelement ausgeblendet ist.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Wird aufgerufen, indem [DoVerbInPlaceActivate](#doverbinplaceactivate) , bevor das Steuerelement direkt aktiviert ist.|  
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Wird aufgerufen, indem [DoVerbOpen](#doverbopen) , bevor das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wurde.|  
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Wird aufgerufen, indem [DoVerbShow](#doverbshow) , bevor das Steuerelement sichtbar gemacht wurde.|  
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Wird aufgerufen, indem [DoVerbUIActivate](#doverbuiactivate) vor der Benutzeroberfläche für das Steuerelement aktiviert wurde.|  
|[IOleObjectImpl::SetClientSite](#setclientsite)|Weist das Steuerelement über die Client-Website im Container.|  
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Empfiehlt ein Farbschema an das Steuerelement-Anwendung, sofern vorhanden. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleObjectImpl::SetExtent](#setextent)|Legt den Umfang der Anzeigebereich des Steuerelements fest.|  
|[IOleObjectImpl::SetHostNames](#sethostnames)|Weist dem Steuerelement den Namen der containeranwendung und Containerdokument an.|  
|[IOleObjectImpl::SetMoniker](#setmoniker)|Weist das Steuerelement was seinen Moniker ist. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleObjectImpl::Unadvise](#unadvise)|Löscht eine Advise-Verbindung mit dem Steuerelement.|  
|[IOleObjectImpl::Update](#update)|Aktualisiert das Steuerelement an. Gibt die ATL-Implementierung `S_OK`.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) -Schnittstelle ist der Prinzipal über die kommuniziert, ein Container mit einem Steuerelement. Klasse `IOleObjectImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
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
 Finden Sie unter [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) im Windows SDK.  
  
##  <a name="close"></a>  IOleObjectImpl::Close  
 Ändert sich der Zustand des Steuerelements von ausgeführt geladen.  
  
```
STDMETHOD(Close)(DWORD dwSaveOption);
```  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement deaktiviert, und zerstört das Steuerelementfenster aus, falls vorhanden. Wenn das Steuerelement-Datenmember-Klasse [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) ist **"true"** und `dwSaveOption` Parameter ist entweder `OLECLOSE_SAVEIFDIRTY` oder `OLECLOSE_PROMPTSAVE`, werden die Eigenschaften des Steuerelements gespeichert vor dem Schließen.  
  
 Die Zeiger frei, die in das Steuerelement Klassendatenmember [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) und [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) freigegeben werden, und die Datenelemente [CComControlBase:: M_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), und [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) festgelegt **"false"**.  
  
 Finden Sie unter [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) im Windows SDK.  
  
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
 Abhängig vom Wert der `iVerb`, eine ATL `DoVerb` Hilfsfunktionen wird wie folgt aufgerufen:  
  
|*iVerb* Wert|DoVerb Hilfsfunktion aufgerufen|  
|-------------------|-----------------------------------|  
|**OLEIVERB_DISCARDUNDOSTATE**|[DoVerbDiscardUndo](#doverbdiscardundo)|  
|`OLEIVERB_HIDE`|[DoVerbHide](#doverbhide)|  
|**OLEIVERB_INPLACEACTIVATE**|[DoVerbInPlaceActivate](#doverbinplaceactivate)|  
|`OLEIVERB_OPEN`|[DoVerbOpen](#doverbopen)|  
|`OLEIVERB_PRIMARY`|[DoVerbPrimary](#doverbprimary)|  
|**OLEIVERB_PROPERTIES**|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|  
|`OLEIVERB_SHOW`|[DoVerbShow](#doverbshow)|  
|`OLEIVERB_UIACTIVATE`|[DoVerbUIActivate](#doverbuiactivate)|  
  
 Finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) im Windows SDK.  
  
##  <a name="doverbdiscardundo"></a>  IOleObjectImpl::DoVerbDiscardUndo  
 Weist das Steuerelement in einem beliebigen Zustand rückgängig zu verwerfen, den sie verwalten.  
  
```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck der Container möchte das Steuerelement in gezeichnet werden soll.  
  
 *hwndParent*  
 [in] Das Handle des Fensters, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="doverbhide"></a>  IOleObjectImpl::DoVerbHide  
 Deaktiviert und das Steuerelement-Benutzeroberfläche entfernt, und blendet das Steuerelement.  
  
```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck der Container möchte das Steuerelement in gezeichnet werden soll.  
  
 *hwndParent*  
 [in] Das Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="doverbinplaceactivate"></a>  IOleObjectImpl::DoVerbInPlaceActivate  
 Führt das Steuerelement und das Fenster installiert, aber das Steuerelement-Benutzeroberfläche wird nicht installiert.  
  
```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck der Container möchte das Steuerelement in gezeichnet werden soll.  
  
 *hwndParent*  
 [in] Das Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Aktiviert das Steuerelement an, durch den Aufruf [CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Wenn der Steuerelementklasse Datenmember `m_bWindowOnly` ist **"true"**, `DoVerbInPlaceActivate` zuerst versucht, das Steuerelement als fensterloses Steuerelement zu aktivieren (möglich nur, wenn der Container unterstützt [IOleInPlaceSiteWindowless ](http://msdn.microsoft.com/library/windows/desktop/ms682300)). Wenn dies fehlschlägt, versucht die Funktion zum Aktivieren des Steuerelements mit erweiterten Funktionen (möglich nur, wenn der Container unterstützt [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461)). Wenn dies fehlschlägt, versucht die Funktion zum Aktivieren des Steuerelements mit keine erweiterten Funktionen (möglich nur, wenn der Container unterstützt [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586)). Wenn die Aktivierung erfolgreich ist, benachrichtigt die Funktion dem Container das Steuerelement aktiviert wurde.  
  
##  <a name="doverbopen"></a>  IOleObjectImpl::DoVerbOpen  
 Bewirkt, dass das Steuerelement bearbeitet werden, öffnen Sie in einem separaten Fenster angezeigt werden.  
  
```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck der Container möchte das Steuerelement in gezeichnet werden soll.  
  
 *hwndParent*  
 [in] Das Handle des Fensters, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="doverbprimary"></a>  IOleObjectImpl::DoVerbPrimary  
 Definiert die Aktion ausgeführt, wenn der Benutzer das Steuerelement doppelklickt.  
  
```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck der Container möchte das Steuerelement in gezeichnet werden soll.  
  
 *hwndParent*  
 [in] Das Handle des Fensters, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig festgelegt, um die Eigenschaftenseiten angezeigt. Sie können dies in der Steuerelementklasse aufzurufenden auf Doppelklicken Sie auf ein anderes Verhalten überschreiben. z. B. spielen Sie ein Video ab, oder wechseln Sie in-Place aktiv.  
  
##  <a name="doverbshow"></a>  IOleObjectImpl::DoVerbShow  
 Weist den Container, um das Steuerelement sichtbar zu machen.  
  
```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck der Container möchte das Steuerelement in gezeichnet werden soll.  
  
 *hwndParent*  
 [in] Das Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
##  <a name="doverbuiactivate"></a>  IOleObjectImpl::DoVerbUIActivate  
 Aktiviert das Steuerelement-Benutzeroberfläche und benachrichtigt dem Container, seine Menüs von zusammengesetzten Menüs ersetzt werden.  
  
```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck der Container möchte das Steuerelement in gezeichnet werden soll.  
  
 *hwndParent*  
 [in] Das Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
##  <a name="enumadvise"></a>  IOleObjectImpl::EnumAdvise  
 Stellt eine Enumeration von registrierten Advise-Verbindungen für das genannte Steuerelement bereit.  
  
```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::EnumAdvise](http://msdn.microsoft.com/library/windows/desktop/ms682355) im Windows SDK.  
  
##  <a name="enumverbs"></a>  IOleObjectImpl::EnumVerbs  
 Stellt eine Enumeration von registrierten Aktionen (Verben) für das genannte Steuerelement durch Aufrufen von **OleRegEnumVerbs**.  
  
```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können Verben RGS-Datei des Projekts hinzufügen. Beispielsweise finden Sie unter CIRCCTL. RGS in der [CIRC](../../visual-cpp-samples.md) Beispiel.  
  
 Finden Sie unter [IOleObject:: EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781) im Windows SDK.  
  
##  <a name="getclientsite"></a>  IOleObjectImpl::GetClientSite  
 Setzt den Zeiger in der Steuerelement-Klassendatenmember [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) in *PpClientSite* und inkrementiert den Verweiszähler für den Zeiger.  
  
```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::GetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms692603) im Windows SDK.  
  
##  <a name="getclipboarddata"></a>  IOleObjectImpl::GetClipboardData  
 Ruft Daten aus der Zwischenablage ab.  
  
```
STDMETHOD(GetClipboardData)(    
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms682288) im Windows SDK.  
  
##  <a name="getextent"></a>  IOleObjectImpl::GetExtent  
 Ruft eine ausgeführte Steuerelement Anzeigegröße in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) ab.  
  
```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Größe wird in der Steuerelement-Klassendatenmember gespeichert [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
 Finden Sie unter [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) im Windows SDK.  
  
##  <a name="getmiscstatus"></a>  IOleObjectImpl::GetMiscStatus  
 Gibt einen Zeiger auf registrierten Statusinformationen für das Steuerelement zurück, durch den Aufruf **OleRegGetMiscStatus**.  
  
```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Statusinformationen handelt es sich um Verhaltensweisen, die durch die Steuerung und Präsentation Daten unterstützt. Sie können Statusinformationen RGS-Datei des Projekts hinzufügen.  
  
 Finden Sie unter [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) im Windows SDK.  
  
##  <a name="getmoniker"></a>  IOleObjectImpl::GetMoniker  
 Ruft das Steuerelement-Moniker ab.  
  
```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::GetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms686576) im Windows SDK.  
  
##  <a name="getuserclassid"></a>  IOleObjectImpl::GetUserClassID  
 Gibt das Steuerelement-Klassen-ID zurück.  
  
```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::GetUserClassID](http://msdn.microsoft.com/library/windows/desktop/ms682313) im Windows SDK.  
  
##  <a name="getusertype"></a>  IOleObjectImpl::GetUserType  
 Gibt das Steuerelement Benutzertypnamens durch Aufrufen von **OleRegGetUserType**.  
  
```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzertyp Name ist für die Anzeige in Benutzeroberflächen Elemente, z. B. Menüs und Dialogfelder verwendet. Sie können die Benutzer-Typnamen in Ihrem Projekt RGS-Datei ändern.  
  
 Finden Sie unter [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) im Windows SDK.  
  
##  <a name="initfromdata"></a>  IOleObjectImpl::InitFromData  
 Initialisiert das Steuerelement aus der ausgewählten Daten.  
  
```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) im Windows SDK.  
  
##  <a name="isuptodate"></a>  IOleObjectImpl::IsUpToDate  
 Überprüft, ob das Steuerelement auf dem neuesten Stand ist.  
  
```
STDMETHOD(IsUpToDate)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) im Windows SDK.  
  
##  <a name="onpostverbdiscardundo"></a>  IOleObjectImpl::OnPostVerbDiscardUndo  
 Wird aufgerufen, indem [DoVerbDiscardUndo](#doverbdiscardundo) nach, dass Sie wieder rückgängig zu machen verworfen wird.  
  
```
HRESULT OnPostVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit den gewünschten Code ausgeführt, nachdem die rückgängig-Zustand verworfen wird.  
  
##  <a name="onpostverbhide"></a>  IOleObjectImpl::OnPostVerbHide  
 Wird aufgerufen, indem [DoVerbHide](#doverbhide) nachdem das Steuerelement ausgeblendet ist.  
  
```
HRESULT OnPostVerbHide();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit den gewünschten Code ausgeführt, nachdem das Steuerelement ausgeblendet ist.  
  
##  <a name="onpostverbinplaceactivate"></a>  IOleObjectImpl::OnPostVerbInPlaceActivate  
 Wird aufgerufen, indem [DoVerbInPlaceActivate](#doverbinplaceactivate) nachdem das Steuerelement direkt aktiviert ist.  
  
```
HRESULT OnPostVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit den gewünschten Code ausgeführt, nachdem das Steuerelement direkt aktiviert ist.  
  
##  <a name="onpostverbopen"></a>  IOleObjectImpl::OnPostVerbOpen  
 Wird aufgerufen, indem [DoVerbOpen](#doverbopen) nachdem das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wurde.  
  
```
HRESULT OnPostVerbOpen();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit zu bearbeitenden ausgeführt, nachdem das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wurde.  
  
##  <a name="onpostverbshow"></a>  IOleObjectImpl::OnPostVerbShow  
 Wird aufgerufen, indem [DoVerbShow](#doverbshow) nachdem das Steuerelement sichtbar gemacht wurde.  
  
```
HRESULT OnPostVerbShow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit dem Code an ausgeführt, nachdem das Steuerelement ist sichtbar gemacht werden sollen.  
  
##  <a name="onpostverbuiactivate"></a>  IOleObjectImpl::OnPostVerbUIActivate  
 Wird aufgerufen, indem [DoVerbUIActivate](#doverbuiactivate) nach der Aktivierung der Benutzeroberfläche des Steuerelements.  
  
```
HRESULT OnPostVerbUIActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit Code, der nach der Aktivierung der Benutzeroberfläche für das Steuerelement ausgeführt werden sollen.  
  
##  <a name="onpreverbdiscardundo"></a>  IOleObjectImpl::OnPreVerbDiscardUndo  
 Wird aufgerufen, indem [DoVerbDiscardUndo](#doverbdiscardundo) vor der Rückgängig Status verworfen wird.  
  
```
HRESULT OnPreVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass die rückgängig-Zustand verworfen werden, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide  
 Wird aufgerufen, indem [DoVerbHide](#doverbhide) , bevor das Steuerelement ausgeblendet ist.  
  
```
HRESULT OnPreVerbHide();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement ausgeblendet wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbinplaceactivate"></a>  IOleObjectImpl::OnPreVerbInPlaceActivate  
 Wird aufgerufen, indem [DoVerbInPlaceActivate](#doverbinplaceactivate) , bevor das Steuerelement direkt aktiviert ist.  
  
```
HRESULT OnPreVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement festliegen aktiviert wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbopen"></a>  IOleObjectImpl::OnPreVerbOpen  
 Wird aufgerufen, indem [DoVerbOpen](#doverbopen) , bevor das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wurde.  
  
```
HRESULT OnPreVerbOpen();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbshow"></a>  IOleObjectImpl::OnPreVerbShow  
 Wird aufgerufen, indem [DoVerbShow](#doverbshow) , bevor das Steuerelement sichtbar gemacht wurde.  
  
```
HRESULT OnPreVerbShow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement sichtbar gemacht wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbuiactivate"></a>  IOleObjectImpl::OnPreVerbUIActivate  
 Wird aufgerufen, indem [DoVerbUIActivate](#doverbuiactivate) vor der Benutzeroberfläche für das Steuerelement aktiviert wurde.  
  
```
HRESULT OnPreVerbUIActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement-Benutzeroberfläche aktiviert wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="setclientsite"></a>  IOleObjectImpl::SetClientSite  
 Weist das Steuerelement über die Client-Website im Container.  
  
```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie dann die Methode gibt `S_OK`.  
  
 Finden Sie unter [IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) im Windows SDK.  
  
##  <a name="setcolorscheme"></a>  IOleObjectImpl::SetColorScheme  
 Empfiehlt ein Farbschema an das Steuerelement-Anwendung, sofern vorhanden.  
  
```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) im Windows SDK.  
  
##  <a name="setextent"></a>  IOleObjectImpl::SetExtent  
 Legt den Umfang der Anzeigebereich des Steuerelements fest.  
  
```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Hinweise  
 Andernfalls `SetExtent` speichert den Wert verweist `psizel` in der Steuerelement-Klassendatenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Dieser Wert ist in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit).  
  
 Wenn das Steuerelement-Datenmember-Klasse [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) ist **"true"**, `SetExtent` speichert auch den Wert verweist `psizel` der Datenmember Klasse [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).  
  
 Wenn das Steuerelement-Datenmember-Klasse [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) ist **"true"**, `SetExtent` Aufrufe `SendOnDataChange` und `SendOnViewChange` benachrichtigt alle Advise-Senken, registriert der Advise-Inhaber, dass die Größe des Steuerelements geändert wurde.  
  
 Finden Sie unter [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) im Windows SDK.  
  
##  <a name="sethostnames"></a>  IOleObjectImpl::SetHostNames  
 Weist dem Steuerelement den Namen der containeranwendung und Containerdokument an.  
  
```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) im Windows SDK.  
  
##  <a name="setmoniker"></a>  IOleObjectImpl::SetMoniker  
 Weist das Steuerelement was seinen Moniker ist.  
  
```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::SetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679671) im Windows SDK.  
  
##  <a name="unadvise"></a>  IOleObjectImpl::Unadvise  
 Löscht die Advise-Verbindung in der Steuerelementklasse gespeicherten `m_spOleAdviseHolder` -Datenmember.  
  
```
STDMETHOD(Unadvise)(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) im Windows SDK.  
  
##  <a name="update"></a>  IOleObjectImpl::Update  
 Aktualisiert das Steuerelement an.  
  
```
STDMETHOD(Update)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::Update](http://msdn.microsoft.com/library/windows/desktop/ms679699) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX-Steuerelemente Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
