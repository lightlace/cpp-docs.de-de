---
title: Klasse IOleObjectImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: b0b471b997bfdb4062f00b40864c347db78b114a
ms.lasthandoff: 02/24/2017

---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl-Klasse
Diese Klasse implementiert **IUnknown** und über die Container, die mit einem Steuerelement kommuniziert die Standardschnittstelle ist.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IOleObjectImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](#advise)|Richtet eine Advise-Verbindung mit dem Steuerelement.|  
|[IOleObjectImpl::Close](#close)|Ändert den Steuerelementzustand aus ausgeführt geladen.|  
|[IOleObjectImpl::DoVerb](#doverb)|Weist das Steuerelement eine der aufgelisteten Aktionen ausführen.|  
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Weist das Steuerelement an jeden rückgängig-Zustand verwerfen, wird.|  
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Weist das Steuerelement an die Benutzeroberfläche aus der Ansicht entfernen.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Führt das Steuerelement und installiert dessen Fenster, jedoch wird die Benutzeroberfläche des Steuerelements nicht installiert.|  
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Bewirkt, dass das Steuerelement öffnen bearbeitet werden, in einem separaten Fenster.|  
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|Führt die angegebene Aktion aus, wenn der Benutzer das Steuerelement doppelklickt. Das Steuerelement definiert die Aktion in der Regel um das Steuerelement direkt zu aktivieren.|  
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Zeigt eine neu eingefügte-Steuerelement für dem Benutzer an.|  
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Aktiviert das Steuerelement direkt und zeigt das Steuerelement-Benutzeroberfläche, z. B. Menüs und Symbolleisten.|  
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Listet die Advise-Verbindungen des Steuerelements.|  
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Listet die Aktionen für das Steuerelement.|  
|[IOleObjectImpl::GetClientSite](#getclientsite)|Ruft des Steuerelements ab.|  
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Ruft Daten aus der Zwischenablage ab. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleObjectImpl::GetExtent](#getextent)|Ruft das Ausmaß der Anzeigebereich des Steuerelements ab.|  
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Ruft den Status des Steuerelements ab.|  
|[IOleObjectImpl::GetMoniker](#getmoniker)|Ruft das Steuerelement-Moniker. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Ruft die Klassen-ID des Steuerelements ab.|  
|[IOleObjectImpl::GetUserType](#getusertype)|Ruft den Namen des Steuerelements Benutzertyp ab.|  
|[IOleObjectImpl::InitFromData](#initfromdata)|Initialisiert das Steuerelement aus den ausgewählten Daten. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Überprüft, ob das Steuerelement auf dem neuesten Stand ist. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Aufgerufen von [DoVerbDiscardUndo](#doverbdiscardundo) nach, wieder rückgängig zu machen verworfen wird.|  
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Aufgerufen von [DoVerbHide](#doverbhide) , nachdem das Steuerelement ausgeblendet ist.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Aufgerufen von [DoVerbInPlaceActivate](#doverbinplaceactivate) , nachdem das Steuerelement direkt aktiviert wird.|  
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Aufgerufen von [DoVerbOpen](#doverbopen) nachdem das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.|  
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Aufgerufen von [DoVerbShow](#doverbshow) , nachdem das Steuerelement sichtbar gemacht wurde.|  
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Aufgerufen von [DoVerbUIActivate](#doverbuiactivate) nach der Aktivierung der Benutzeroberfläche des Steuerelements.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Aufgerufen von [DoVerbDiscardUndo](#doverbdiscardundo) vor das Rückgängig Zustand verworfen wird.|  
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Aufgerufen von [DoVerbHide](#doverbhide) , bevor das Steuerelement ausgeblendet ist.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Aufgerufen von [DoVerbInPlaceActivate](#doverbinplaceactivate) , bevor das Steuerelement direkt aktiviert wird.|  
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Aufgerufen von [DoVerbOpen](#doverbopen) , bevor das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.|  
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Aufgerufen von [DoVerbShow](#doverbshow) , bevor das Steuerelement sichtbar gemacht wurde.|  
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Aufgerufen von [DoVerbUIActivate](#doverbuiactivate) vor der Benutzeroberfläche des Steuerelements aktiviert wurde.|  
|[IOleObjectImpl::SetClientSite](#setclientsite)|Weist das Steuerelement über seine Client-Website im Container.|  
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Empfiehlt ein Farbschema für das Steuerelement Anwendung ggf.. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleObjectImpl::SetExtent](#setextent)|Legt das Ausmaß der Anzeigebereich des Steuerelements fest.|  
|[IOleObjectImpl::SetHostNames](#sethostnames)|Weist das Steuerelement die Namen der Container-Anwendung und des Containerdokuments.|  
|[IOleObjectImpl::SetMoniker](#setmoniker)|Weist das Steuerelement was seinen Moniker ist. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleObjectImpl::Unadvise](#unadvise)|Löscht eine Advise-Verbindung mit dem Steuerelement.|  
|[IOleObjectImpl::Update](#update)|Aktualisiert das Steuerelement. Der ATL-Implementierung zurückgegeben `S_OK`.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) -Schnittstelle ist der Prinzipal über die Container, die mit einem Steuerelement kommuniziert. Klasse `IOleObjectImpl` bietet eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="advise"></a>IOleObjectImpl::Advise  
 Richtet eine Advise-Verbindung mit dem Steuerelement.  
  
```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="close"></a>IOleObjectImpl::Close  
 Ändert den Steuerelementzustand aus ausgeführt geladen.  
  
```
STDMETHOD(Close)(DWORD dwSaveOption);
```  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement deaktiviert und das Steuerelementfenster zerstört, wenn es vorhanden ist. Wenn das Steuerelement Datenmember-Klasse [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) ist **TRUE** und `dwSaveOption` Parameter ist entweder `OLECLOSE_SAVEIFDIRTY` oder `OLECLOSE_PROMPTSAVE`, Eigenschaften des Steuerelements vor dem Schließen gespeichert werden.  
  
 Der Zeiger frei, die in das Steuerelement Klassendatenmember [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) und [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) freigegeben werden, und die Datenelemente [CComControlBase::m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), und [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) festgelegt **FALSE**.  
  
 Finden Sie unter [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="doverb"></a>IOleObjectImpl::DoVerb  
 Weist das Steuerelement eine der aufgelisteten Aktionen ausführen.  
  
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
 Abhängig vom Wert der `iVerb`, eines der ATL `DoVerb` Hilfsfunktionen wird wie folgt aufgerufen:  
  
|*iVerb* Wert|DoVerb-Hilfsfunktion aufgerufen|  
|-------------------|-----------------------------------|  
|**OLEIVERB_DISCARDUNDOSTATE**|[DoVerbDiscardUndo](#doverbdiscardundo)|  
|`OLEIVERB_HIDE`|[DoVerbHide](#doverbhide)|  
|**OLEIVERB_INPLACEACTIVATE**|[DoVerbInPlaceActivate](#doverbinplaceactivate)|  
|`OLEIVERB_OPEN`|[DoVerbOpen](#doverbopen)|  
|`OLEIVERB_PRIMARY`|[DoVerbPrimary](#doverbprimary)|  
|**OLEIVERB_PROPERTIES**|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|  
|`OLEIVERB_SHOW`|[DoVerbShow](#doverbshow)|  
|`OLEIVERB_UIACTIVATE`|[DoVerbUIActivate](#doverbuiactivate)|  
  
 Finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="doverbdiscardundo"></a>IOleObjectImpl::DoVerbDiscardUndo  
 Weist das Steuerelement an jeden rückgängig-Zustand verwerfen, wird.  
  
```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck Container möchte das Steuerelement in gezeichnet.  
  
 *hwndParent*  
 [in] Handle des Fensters, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="doverbhide"></a>IOleObjectImpl::DoVerbHide  
 Deaktiviert und entfernt die Steuerelement-Benutzeroberfläche, und blendet das Steuerelement.  
  
```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck Container möchte das Steuerelement in gezeichnet.  
  
 *hwndParent*  
 [in] Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="doverbinplaceactivate"></a>IOleObjectImpl::DoVerbInPlaceActivate  
 Führt das Steuerelement und installiert dessen Fenster, jedoch wird die Benutzeroberfläche des Steuerelements nicht installiert.  
  
```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck Container möchte das Steuerelement in gezeichnet.  
  
 *hwndParent*  
 [in] Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Aktiviert das Steuerelement an, durch Aufrufen von [CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Wenn der Steuerelementklasse Datenmember `m_bWindowOnly` ist **TRUE**, `DoVerbInPlaceActivate` zuerst versucht, das Steuerelement als fensterloses Steuerelement zu aktivieren (möglich nur, wenn der Container unterstützt [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)). Wenn dies fehlschlägt, versucht die Funktion zum Aktivieren des Steuerelements mit erweiterten Funktionen (möglich nur, wenn der Container unterstützt [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461)). Wenn dies fehlschlägt, versucht die Funktion zum Aktivieren des Steuerelements ohne erweiterte Features (möglich nur, wenn der Container unterstützt [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586)). Wenn die Aktivierung erfolgreich ist, benachrichtigt die Funktion dem Container das Steuerelement aktiviert wurde.  
  
##  <a name="doverbopen"></a>IOleObjectImpl::DoVerbOpen  
 Bewirkt, dass das Steuerelement öffnen bearbeitet werden, in einem separaten Fenster.  
  
```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck Container möchte das Steuerelement in gezeichnet.  
  
 *hwndParent*  
 [in] Handle des Fensters, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="doverbprimary"></a>IOleObjectImpl::DoVerbPrimary  
 Definiert die Aktion ausgeführt, wenn der Benutzer auf das Steuerelement doppelklickt.  
  
```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck Container möchte das Steuerelement in gezeichnet.  
  
 *hwndParent*  
 [in] Handle des Fensters, das das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie in der Standardeinstellung auf den Eigenschaftenseiten angezeigt. Sie können dies in der Steuerelementklasse aufzurufenden ein anderes Verhalten auf Doppelklicken überschreiben. z. B. spielen Sie ein Video ab, oder wechseln Sie in-Place aktiv.  
  
##  <a name="doverbshow"></a>IOleObjectImpl::DoVerbShow  
 Weist den Container aus, um das Steuerelement sichtbar zu machen.  
  
```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck Container möchte das Steuerelement in gezeichnet.  
  
 *hwndParent*  
 [in] Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
##  <a name="doverbuiactivate"></a>IOleObjectImpl::DoVerbUIActivate  
 Die Steuerelement-Benutzeroberfläche aktiviert, und zeigt dem Container an, dass die Menüs von zusammengesetzten Menüs ersetzt werden.  
  
```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parameter  
 `prcPosRec`  
 [in] Zeiger auf das Rechteck Container möchte das Steuerelement in gezeichnet.  
  
 *hwndParent*  
 [in] Handle des Fensters, das das Steuerelement enthält. In der ATL-Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
##  <a name="enumadvise"></a>IOleObjectImpl::EnumAdvise  
 Stellt eine Enumeration von registrierten Advise-Verbindungen für dieses Steuerelement.  
  
```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::EnumAdvise](http://msdn.microsoft.com/library/windows/desktop/ms682355) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="enumverbs"></a>IOleObjectImpl::EnumVerbs  
 Stellt eine Enumeration der registrierten Aktionen (Verben) für dieses Steuerelement durch Aufrufen von **OleRegEnumVerbs**.  
  
```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können Verben .rgs-Datei des Projekts hinzufügen. Beispielsweise finden Sie unter CIRCCTL. RGS in der [CIRC](../../visual-cpp-samples.md) Beispiel.  
  
 Finden Sie unter [IOleObject:: EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclientsite"></a>IOleObjectImpl::GetClientSite  
 Setzt den Mauszeiger in die Steuerelement-Klassendatenmember [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) in *PpClientSite* und erhöht den Verweiszähler für den Zeiger.  
  
```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::GetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms692603) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclipboarddata"></a>IOleObjectImpl::GetClipboardData  
 Ruft Daten aus der Zwischenablage ab.  
  
```
STDMETHOD(GetClipboardData)(    
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms682288) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getextent"></a>IOleObjectImpl::GetExtent  
 Ruft eine ausgeführte Steuerelement Anzeigegröße in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) ab.  
  
```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Größe wird gespeichert, in der Steuerelement-Klassendatenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
 Finden Sie unter [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getmiscstatus"></a>IOleObjectImpl::GetMiscStatus  
 Gibt einen Zeiger auf registrierte Statusinformationen für das Steuerelement durch Aufrufen von **OleRegGetMiscStatus**.  
  
```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Statusinformationen umfasst Verhaltensweisen, die durch die Steuerung und Präsentation Daten unterstützt. Sie können Statusinformationen .rgs-Datei des Projekts hinzufügen.  
  
 Finden Sie unter [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getmoniker"></a>IOleObjectImpl::GetMoniker  
 Ruft das Steuerelement-Moniker.  
  
```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::GetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms686576) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getuserclassid"></a>IOleObjectImpl::GetUserClassID  
 Gibt die Klassen-ID des Steuerelements zurück.  
  
```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::GetUserClassID](http://msdn.microsoft.com/library/windows/desktop/ms682313) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getusertype"></a>IOleObjectImpl::GetUserType  
 Gibt den Namen des Steuerelements Benutzertyp durch Aufrufen von **OleRegGetUserType**.  
  
```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzertyp Name ist für die Anzeige in Benutzeroberflächen Elemente wie Menüs und Dialogfelder verwendet. Sie können die Benutzer-Typnamen in .rgs-Datei des Projekts ändern.  
  
 Finden Sie unter [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="initfromdata"></a>IOleObjectImpl::InitFromData  
 Initialisiert das Steuerelement aus den ausgewählten Daten.  
  
```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isuptodate"></a>IOleObjectImpl::IsUpToDate  
 Überprüft, ob das Steuerelement auf dem neuesten Stand ist.  
  
```
STDMETHOD(IsUpToDate)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onpostverbdiscardundo"></a>IOleObjectImpl::OnPostVerbDiscardUndo  
 Aufgerufen von [DoVerbDiscardUndo](#doverbdiscardundo) nach, wieder rückgängig zu machen verworfen wird.  
  
```
HRESULT OnPostVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit den gewünschten Code ausgeführt, nachdem der Rückgängig-Zustand verworfen wurde.  
  
##  <a name="onpostverbhide"></a>IOleObjectImpl::OnPostVerbHide  
 Aufgerufen von [DoVerbHide](#doverbhide) , nachdem das Steuerelement ausgeblendet ist.  
  
```
HRESULT OnPostVerbHide();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit den gewünschten Code ausgeführt, nachdem das Steuerelement ausgeblendet ist.  
  
##  <a name="onpostverbinplaceactivate"></a>IOleObjectImpl::OnPostVerbInPlaceActivate  
 Aufgerufen von [DoVerbInPlaceActivate](#doverbinplaceactivate) , nachdem das Steuerelement direkt aktiviert wird.  
  
```
HRESULT OnPostVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit den gewünschten Code ausgeführt, nachdem das Steuerelement direkt aktiviert wird.  
  
##  <a name="onpostverbopen"></a>IOleObjectImpl::OnPostVerbOpen  
 Aufgerufen von [DoVerbOpen](#doverbopen) nachdem das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.  
  
```
HRESULT OnPostVerbOpen();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit dem zu bearbeitenden ausgeführt, nachdem das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.  
  
##  <a name="onpostverbshow"></a>IOleObjectImpl::OnPostVerbShow  
 Aufgerufen von [DoVerbShow](#doverbshow) , nachdem das Steuerelement sichtbar gemacht wurde.  
  
```
HRESULT OnPostVerbShow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit dem zu bearbeitenden ausgeführt, nachdem das Steuerelement sichtbar gemacht wurde.  
  
##  <a name="onpostverbuiactivate"></a>IOleObjectImpl::OnPostVerbUIActivate  
 Aufgerufen von [DoVerbUIActivate](#doverbuiactivate) nach der Aktivierung der Benutzeroberfläche des Steuerelements.  
  
```
HRESULT OnPostVerbUIActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit Code, der nach der Aktivierung der Benutzeroberfläche des Steuerelements ausgeführt werden soll.  
  
##  <a name="onpreverbdiscardundo"></a>IOleObjectImpl::OnPreVerbDiscardUndo  
 Aufgerufen von [DoVerbDiscardUndo](#doverbdiscardundo) vor das Rückgängig Zustand verworfen wird.  
  
```
HRESULT OnPreVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass wieder rückgängig zu machen, die verworfen wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbhide"></a>IOleObjectImpl::OnPreVerbHide  
 Aufgerufen von [DoVerbHide](#doverbhide) , bevor das Steuerelement ausgeblendet ist.  
  
```
HRESULT OnPreVerbHide();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement ausgeblendet wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbinplaceactivate"></a>IOleObjectImpl::OnPreVerbInPlaceActivate  
 Aufgerufen von [DoVerbInPlaceActivate](#doverbinplaceactivate) , bevor das Steuerelement direkt aktiviert wird.  
  
```
HRESULT OnPreVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement an aktiviert wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbopen"></a>IOleObjectImpl::OnPreVerbOpen  
 Aufgerufen von [DoVerbOpen](#doverbopen) , bevor das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wurde.  
  
```
HRESULT OnPreVerbOpen();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement für die Bearbeitung in einem separaten Fenster geöffnet wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbshow"></a>IOleObjectImpl::OnPreVerbShow  
 Aufgerufen von [DoVerbShow](#doverbshow) , bevor das Steuerelement sichtbar gemacht wurde.  
  
```
HRESULT OnPreVerbShow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement sichtbar gemacht wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="onpreverbuiactivate"></a>IOleObjectImpl::OnPreVerbUIActivate  
 Aufgerufen von [DoVerbUIActivate](#doverbuiactivate) vor der Benutzeroberfläche des Steuerelements aktiviert wurde.  
  
```
HRESULT OnPreVerbUIActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu verhindern, dass das Steuerelement-Benutzeroberfläche aktiviert wird, überschreiben Sie diese Methode, um einen HRESULT-Fehler zurück.  
  
##  <a name="setclientsite"></a>IOleObjectImpl::SetClientSite  
 Weist das Steuerelement über seine Client-Website im Container.  
  
```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Anschließend gibt die Methode `S_OK`.  
  
 Finden Sie unter [IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setcolorscheme"></a>IOleObjectImpl::SetColorScheme  
 Empfiehlt ein Farbschema für das Steuerelement Anwendung ggf..  
  
```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setextent"></a>IOleObjectImpl::SetExtent  
 Legt das Ausmaß der Anzeigebereich des Steuerelements fest.  
  
```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Hinweise  
 Andernfalls `SetExtent` speichert den Wert auf den `psizel` der Control-Klasse Datenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Dieser Wert ist in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit).  
  
 Wenn das Steuerelement Datenmember-Klasse [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) ist **TRUE**, `SetExtent` auch speichert den Wert, der auf den `psizel` der Control-Klasse Datenmember [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).  
  
 Wenn das Steuerelement Datenmember-Klasse [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) ist **TRUE**, `SetExtent` Aufrufe `SendOnDataChange` und `SendOnViewChange` benachrichtigt alle Advise-Senken registriert den Inhaber der anweisen, die die Größe des Steuerelements geändert wurde.  
  
 Finden Sie unter [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="sethostnames"></a>IOleObjectImpl::SetHostNames  
 Weist das Steuerelement die Namen der Container-Anwendung und des Containerdokuments.  
  
```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setmoniker"></a>IOleObjectImpl::SetMoniker  
 Weist das Steuerelement was seinen Moniker ist.  
  
```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::SetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679671) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="unadvise"></a>IOleObjectImpl::Unadvise  
 Löscht die Advise-Verbindung in der Steuerelementklasse gespeicherte `m_spOleAdviseHolder` -Datenmember.  
  
```
STDMETHOD(Unadvise)(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="update"></a>IOleObjectImpl::Update  
 Aktualisiert das Steuerelement.  
  
```
STDMETHOD(Update)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleObject::Update](http://msdn.microsoft.com/library/windows/desktop/ms679699) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX-Steuerelemente Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

