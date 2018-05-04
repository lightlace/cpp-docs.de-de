---
title: IViewObjectExImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c51bc9e5feb02d837c37341b82a1fc19a3cea558
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl-Klasse
Diese Klasse implementiert **IUnknown** standardmäßigen Implementierungen von sowie die [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), und [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)Schnittstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IViewObjectExImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|Zeichnet eine Darstellung des Steuerelements auf einem Gerätekontext.|  
|[IViewObjectExImpl::Freeze](#freeze)|Die gezeichnete Darstellung eines Steuerelements fixiert, damit sich diese nicht bis zum Ändern einer `Unfreeze`. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|Ruft eine vorhandene Advise-Senke-Verbindung auf das Steuerelement ab, sofern vorhanden.|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Gibt die logische Palette, die vom Steuerelement zum Zeichnen verwendeten zurück. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetExtent](#getextent)|Ruft das Steuerelement der Anzeigegröße in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) aus der Steuerelement-Klassendatenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Enthält Hinweise der größenanpassung aus dem Container für das Objekt, das verwendet wird, wenn der Benutzer die Größe ändern.|  
|[IViewObjectExImpl::GetRect](#getrect)|Gibt ein Rechteck, das einen angeforderte zeichnen Aspekt beschreiben. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Gibt Informationen über die Deckkraft des Objekts und welche zeichnen Aspekte unterstützt werden.|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Überprüft, ob der angegebene Punkt im angegebenen Rechteck ist, und gibt eine [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) Wert in `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Überprüft, ob das Steuerelement Anzeigerechteck überschneidet sich mit einem beliebigen Punkt in der angegebenen Position Rechteck und gibt eine **HITRESULT** Wert in `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|Richtet eine Verbindung zwischen dem Steuerelement und einer Advise-Senke, damit die Senke zu Änderungen in der Steuerelementansicht des benachrichtigt werden kann.|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Hebt die Fixierung der gezeichneten Darstellung des Steuerelements. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), und [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) Schnittstellen ermöglichen ein Steuerelement selbst direkt anzeigen sowie zum Erstellen und Verwalten einer Advise-Senke benachrichtigen der Container für Änderungen in der Steuerelementanzeige. Die **IViewObjectEx** Schnittstelle bietet Unterstützung für erweiterten Steuerelements-Funktionen, z. B. flimmerfreier zeichnen, viereckig noch transparent Steuerelemente und Treffertests (z. B., wie weit ein Mausklick sein muss auf berücksichtigt werden das Steuerelement). Klasse `IViewObjectExImpl` stellt eine Standardimplementierung dieser Schnittstellen und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="draw"></a>  IViewObjectExImpl::Draw  
 Zeichnet eine Darstellung des Steuerelements auf einem Gerätekontext.  
  
```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft **CComControl::OnDrawAdvanced** die wiederum ruft der Steuerelementklasse `OnDraw` Methode. Ein `OnDraw` Methode wird automatisch bei der Erstellung des Steuerelements mit der ATL-Steuerelement-Assistent für die Steuerelementklasse hinzugefügt. Der Assistent standardmäßig `OnDraw` zeichnet ein Rechteck mit der Bezeichnung "ATL 3.0".  
  
 Finden Sie unter [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) im Windows SDK.  
  
##  <a name="freeze"></a>  IViewObjectExImpl::Freeze  
 Die gezeichnete Darstellung eines Steuerelements fixiert, damit sich diese nicht bis zum Ändern einer `Unfreeze`. Gibt die ATL-Implementierung **E_NOTIMPL**.  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728) im Windows SDK.  
  
##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise  
 Ruft eine vorhandene Advise-Senke-Verbindung auf das Steuerelement ab, sofern vorhanden.  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Advise-Senke befindet sich in der Steuerelement-Klassendatenmember [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).  
  
 Finden Sie unter [IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772) im Windows SDK.  
  
##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet  
 Gibt die logische Palette, die vom Steuerelement zum Zeichnen verwendeten zurück. Gibt die ATL-Implementierung **E_NOTIMPL**.  
  
```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553) im Windows SDK.  
  
##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent  
 Ruft das Steuerelement der Anzeigegröße in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) aus der Steuerelement-Klassendatenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) im Windows SDK.  
  
##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent  
 Enthält Hinweise der größenanpassung aus dem Container für das Objekt, das verwendet wird, wenn der Benutzer die Größe ändern.  
  
```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `dwAspect` ist `DVASPECT_CONTENT` und *pExtentInfo -> DwExtentMode* ist **DVEXTENT_CONTENT**, legt * `psizel` Datenmember der Steuerelementklasse [CComControlBase: : M_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). Andernfalls wird einen Fehler zurückgegeben `HRESULT`.  
  
 Finden Sie unter [IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718) im Windows SDK.  
  
##  <a name="getrect"></a>  IViewObjectExImpl::GetRect  
 Gibt ein Rechteck, das einen angeforderte zeichnen Aspekt beschreiben. Gibt die ATL-Implementierung **E_NOTIMPL**.  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246) im Windows SDK.  
  
##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus  
 Gibt Informationen über die Deckkraft des Objekts und welche zeichnen Aspekte unterstützt werden.  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig legt ATL `pdwStatus` um anzugeben, dass das Steuerelement unterstützt **VIEWSTATUS_OPAQUE** (mögliche Werte sind in der [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) Enumeration).  
  
 Finden Sie unter [IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371) im Windows SDK.  
  
##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint  
 Überprüft, ob der angegebene Punkt im angegebenen Rechteck ist, und gibt eine [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) Wert in `pHitResult`.  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Hinweise  
 Der Wert kann entweder **HITRESULT_HIT** oder **HITRESULT_OUTSIDE**.  
  
 Wenn `dwAspect` gleich [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), gibt die Methode `S_OK`. Andernfalls der Methodenrückgabe **E_FAIL**.  
  
 Finden Sie unter [IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209) im Windows SDK.  
  
##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect  
 Überprüft, ob das Steuerelement Anzeigerechteck überschneidet sich mit einem beliebigen Punkt in der angegebenen Position Rechteck und gibt eine [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) Wert in `pHitResult`.  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Hinweise  
 Der Wert kann entweder **HITRESULT_HIT** oder **HITRESULT_OUTSIDE**.  
  
 Wenn `dwAspect` gleich [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), gibt die Methode `S_OK`. Andernfalls der Methodenrückgabe **E_FAIL**.  
  
 Finden Sie unter [IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797) im Windows SDK.  
  
##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise  
 Richtet eine Verbindung zwischen dem Steuerelement und einer Advise-Senke, damit die Senke zu Änderungen in der Steuerelementansicht des benachrichtigt werden kann.  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>Hinweise  

 Der Zeiger auf die [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle auf die Advise-Senke befindet sich in der Steuerelement-Klassendatenmember [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).  

  
 Finden Sie unter [IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950) im Windows SDK.  
  
##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze  
 Hebt die Fixierung der gezeichneten Darstellung des Steuerelements. Gibt die ATL-Implementierung **E_NOTIMPL**.  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObject::Unfreeze](http://msdn.microsoft.com/library/windows/desktop/ms686641) im Windows SDK.  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 Implementieren Sie diese Methode, um das diesem Objekt zugeordnete Handle nicht geschlossen.  
  
```
HRESULT CloseHandle(HANDLE hHandle);
```  
  
### <a name="parameters"></a>Parameter  
 *hHandle*  
 Das Handle geschlossen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Geben Sie S_OK zurück, auf Erfolg oder einen HRESULT-Fehler bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle übergeben an diese Methode wurde zuvor mit diesem Objekt verknüpften durch einen Aufruf von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung der `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 Implementieren Sie diese Methode, um Code auszuführen, wenn das Handle, das diesem Objekt zugeordneten signalisiert wird.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Parameter  
 `dwParam`  
 Der Benutzerparameter.  
  
 `hObject`  
 Das Handle, das signalisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Geben Sie S_OK zurück, auf Erfolg oder einen HRESULT-Fehler bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle und die DWORD/Zeiger an diese Methode übergebenen wurden zuvor mit diesem Objekt durch einen Aufruf von verknüpften [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung der `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX-Steuerelemente Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Lernprogramm](../../atl/active-template-library-atl-tutorial.md)   
 [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
