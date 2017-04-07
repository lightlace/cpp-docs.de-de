---
title: Klasse IViewObjectExImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
ms.openlocfilehash: 2b585a056324507cc631e64e6dbe9d0ed610361d
ms.lasthandoff: 02/24/2017

---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl-Klasse
Diese Klasse implementiert **IUnknown** und stellt mit der der [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), und [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) Schnittstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IViewObjectExImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|Zeichnet eine Darstellung des Steuerelements auf einem Gerätekontext.|  
|[IViewObjectExImpl::Freeze](#freeze)|Die gezeichnete Darstellung eines Steuerelements fixiert, damit es nicht bis zum Ändern einer `Unfreeze`. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|Ruft eine vorhandene Verbindung der Advise-Senke für das Steuerelement ab, sofern vorhanden.|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Gibt die logische Palette, die vom Steuerelement zum Zeichnen verwendeten zurück. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetExtent](#getextent)|Die Größe des Steuerelements anzeigen in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) aus der Steuerelement-Klassendatenmember abgerufen [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Enthält Größenhinweise auf aus dem Container für das Objekt verwenden, da der Benutzer die Größe ändert.|  
|[IViewObjectExImpl::GetRect](#getrect)|Gibt ein Rechteck beschreiben einen Aspekt des angeforderten zeichnen. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Gibt Informationen über die Durchlässigkeit des Objekts und welche zeichnen Aspekte unterstützt werden.|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Überprüft, ob der angegebene Punkt im angegebenen Rechteck ist, und gibt eine [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) Wert in `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Überprüft, ob das Steuerelement Anzeigerechteck überschneidet sich mit einem beliebigen Punkt in der angegebenen Position Rechteck und gibt eine **HITRESULT** Wert in `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|Richtet eine Verbindung zwischen dem Steuerelement und einer Advise-Senke, sodass die Senke zu Änderungen in der Ansicht des Steuerelements benachrichtigt werden kann.|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Hebt die Fixierung der gezeichneten Darstellung des Steuerelements. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), und [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) Schnittstellen kann ein Steuerelement zum selbst direkt anzeigen und zum Erstellen und Verwalten einer Advise-Senke, um den Container der Änderungen in der Steuerelementanzeige zu benachrichtigen. Die **IViewObjectEx** Schnittstelle bietet Unterstützung für erweiterte Steuerelement Features wie flimmerfreie zeichnen, Steuerelemente nicht rechteckige und transparent und Treffertests (z. B. wie schließen ein Mausklick sein muss auf dem Steuerelement berücksichtigt werden). Klasse `IViewObjectExImpl` bietet eine Standardimplementierung dieser Schnittstellen und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="draw"></a>IViewObjectExImpl::Draw  
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
 Diese Methode ruft **CComControl::OnDrawAdvanced** die wiederum ruft der Steuerelementklasse `OnDraw` Methode. Eine `OnDraw` Methode wird automatisch auf eine Klasse hinzugefügt, wenn Sie das Steuerelement mit der ATL-Steuerelement-Assistenten erstellen. Der Assistent standardmäßig `OnDraw` zeichnet ein Rechteck mit der Bezeichnung "ATL 3.0".  
  
 Finden Sie unter [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="freeze"></a>IViewObjectExImpl::Freeze  
 Die gezeichnete Darstellung eines Steuerelements fixiert, damit es nicht bis zum Ändern einer `Unfreeze`. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getadvise"></a>IViewObjectExImpl::GetAdvise  
 Ruft eine vorhandene Verbindung der Advise-Senke für das Steuerelement ab, sofern vorhanden.  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Advise-Senke befindet sich in der Steuerelement-Klassendatenmember [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).  
  
 Finden Sie unter [IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcolorset"></a>IViewObjectExImpl::GetColorSet  
 Gibt die logische Palette, die vom Steuerelement zum Zeichnen verwendeten zurück. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.  
  
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
 Finden Sie unter [IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getextent"></a>IViewObjectExImpl::GetExtent  
 Die Größe des Steuerelements anzeigen in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) aus der Steuerelement-Klassendatenmember abgerufen [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnaturalextent"></a>IViewObjectExImpl::GetNaturalExtent  
 Enthält Größenhinweise auf aus dem Container für das Objekt verwenden, da der Benutzer die Größe ändert.  
  
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
 Wenn `dwAspect` ist `DVASPECT_CONTENT` und *pExtentInfo-> DwExtentMode* ist **DVEXTENT_CONTENT**, legt * `psizel` der Steuerelementklasse Datenelement [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). Andernfalls wird einen Fehler zurückgegeben `HRESULT`.  
  
 Finden Sie unter [IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getrect"></a>IViewObjectExImpl::GetRect  
 Gibt ein Rechteck beschreiben einen Aspekt des angeforderten zeichnen. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getviewstatus"></a>IViewObjectExImpl::GetViewStatus  
 Gibt Informationen über die Durchlässigkeit des Objekts und welche zeichnen Aspekte unterstützt werden.  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig legt ATL `pdwStatus` an, dass das Steuerelement unterstützt **VIEWSTATUS_OPAQUE** (mögliche Werte sind in der [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) Enumeration).  
  
 Finden Sie unter [IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="queryhitpoint"></a>IViewObjectExImpl::QueryHitPoint  
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
  
 Wenn `dwAspect` gleich [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), gibt die Methode `S_OK`. Die Methode andernfalls **E_FAIL**.  
  
 Finden Sie unter [IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="queryhitrect"></a>IViewObjectExImpl::QueryHitRect  
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
  
 Wenn `dwAspect` gleich [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), gibt die Methode `S_OK`. Die Methode andernfalls **E_FAIL**.  
  
 Finden Sie unter [IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setadvise"></a>IViewObjectExImpl::SetAdvise  
 Richtet eine Verbindung zwischen dem Steuerelement und einer Advise-Senke, sodass die Senke zu Änderungen in der Ansicht des Steuerelements benachrichtigt werden kann.  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>Hinweise  

 Der Zeiger auf die [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle auf die Advise-Senke befindet sich in der Steuerelement-Klassendatenmember [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).  

  
 Finden Sie unter [IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="unfreeze"></a>IViewObjectExImpl::Unfreeze  
 Hebt die Fixierung der gezeichneten Darstellung des Steuerelements. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IViewObject::Unfreeze](http://msdn.microsoft.com/library/windows/desktop/ms686641) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 Implementieren Sie diese Methode, um das diesem Objekt zugeordnete Handle zu schließen.  
  
```
HRESULT CloseHandle(HANDLE hHandle);
```  
  
### <a name="parameters"></a>Parameter  
 *hHandle*  
 Das Handle geschlossen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das an diese Methode übergebene Handle wurde zuvor mit diesem Objekt verknüpften durch einen Aufruf von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung von `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities&#135;](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>IWorkerThreadClient::Execute  
 Implementieren Sie diese Methode, um Code auszuführen, wenn das Handle, das diesem Objekt zugeordnete signalisiert wird.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Parameter  
 `dwParam`  
 Der Benutzerparameter.  
  
 `hObject`  
 Das Handle, das signalisiert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle und DWORD/Zeiger an diese Methode übergebenen wurden zuvor mit diesem Objekt verknüpften durch einen Aufruf von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Beispiel  
 Der folgende Code zeigt eine einfache Implementierung von `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities&#136;](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX-Steuerelemente Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Lernprogramm](../../atl/active-template-library-atl-tutorial.md)   
 [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

